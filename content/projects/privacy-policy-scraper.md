---
title: "Privacy Policy Web Scraper"
date: ""
description: "A program that breaks down and organizes information about privacy policies."
ShowToc: true
---

* Read more about the result: [click here](https://coreyst.one/projects/privacy-policy-directory/)

## Demo
{{< figure align=left src="/images/scraper-demo.gif" >}}


## How it works
The program reads-in a CSV file with a list of companies and their associated privacy policies to scrape. For example: the [list of data brokers](https://oag.ca.gov/data-brokers) registered with the California OAG. It outputs fields of interest that may be useful for a data subject trying to exercise their rights with the company.



| Company Name         | Privacy Policy URL |
|--------------|---------|
| McDonald's | https://www.mcdonalds.com/us/en-us/privacy.html   |

I use the [`pandas`](https://pypi.org/project/pandas/) library to read the CSV and store it as a `DataFrame` object (df).


``` python
df = pd.read_csv(input_file_path)
```

I iterate over the DataFrame and try to fetch each page using `requests` on the associated privacy policy's URL. 

Some websites do not play nice, so some exception handling is required:
* `Timeout`: I noticed that a lot of requests were hanging because websites would not respond to the request, so I used this argument to skip requests that are not quickly handled. 
* `HTTP 403 status code`: The request was forbidden
* `HTTP 406 status code`: The request was rejected by the server

A response status code of `HTTP 200 OK` means the request was successful and things are ready to go. I used the [`beautifulsoup4`](https://pypi.org/project/beautifulsoup4/) library to scrape the web page and fetch the page text for parsing.


``` python
for row in df.itertuples():
        company_name       = row.Company
        privacy_policy_url = row.PrivacyPolicy

        try:
            page = requests.get(privacy_policy_url, timeout=3)  # 3 second timeout

        if page.status_code == 200:
            print("Connection successful (HTTP 200 OK). Begin parsing.")
            soup = BeautifulSoup(page.content, features="html.parser")
            soup_string = str(soup)

            page_text = soup.get_text()

```

From here I use a series of [regular expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) to parse the page and find anything I want that has a distinct, repeatable structure that would be easy to consistently locate across multiple sites. The specific pieces of information that I'm interested in are:
* Contact email address
* Contact phone number
* A request form 
* A request mechanism/vendor
* Any mention of various US state privacy laws or residents of those states
* Any mention of Do Not Track/Global Privacy Control
* The date the policy was published/updated
* A link to a [CCPA metrics](https://www.datagrail.io/blog/privacy-trends/cpra-expands-the-ccpas-metrics-reporting-requirements/) page
* Any mention of certification with the [Data Privacy Framework](https://www.dataprivacyframework.gov/s/) (previously the US Privacy Shield)


For fields like an email address or phone number, a match for a single item (like `privacy@company.com`) will be inserted back into the CSV. A {set} of potential values will be returned if multiple matches were found, otherwise the cell will be blank if nothing was found.

``` python
def get_potential_emails(soup_string):
    """
    Find any email addresses within the page
    """
    emails = re.findall(r'[a-z0-9\.\-+_]+@[a-z0-9\.\-+_]+\.[a-z]+', soup_string)
    emails = set(emails)
    print("Unique emails found:", emails) if(len(emails) > 0) else print("Email address not found.")

    if len(emails) == 1:
        return emails.pop()
    elif len(emails) == 0:
        return ""
    else:
        return emails   # Multiple emails found: requires manual review
```

A match for a web form will return the URL of a privacy web form that a company has created to direct data subjects to submit requests. Here is an example [OneTrust privacy web form](https://privacyportal-cdn.onetrust.com/dsarwebform/37bcc497-a196-48f1-a08b-e897b5a77859/08a01c64-41fd-4b4e-9d42-cde44371a422.html) (courtest of OneTrust itself) that would be identified.

``` python
df.at[row.Index, "RequestForm"] = get_potential_request_form(soup) # Returns web form URL
```

Searches for specific states/laws will return a boolean `True` or `False` that simply indicate if a policy mentions a law or if residents of a particular state have special rights. 

The pattern for the various states is basically as follows:
```python
regex = re.compile(r'(Utah( Consumer Privacy Act)?)|(\(?U\.?C\.?P\.?A\.?\)?)')
```

For example, residents of "California" have special rights outlined by the "CCPA".

``` python
df.at[row.Index, "CA"] = check_ccpa(page_text) # Returns T/F
```

The results of each search are inserted into the corresponding column in the CSV for that company. Manual review is required to verify results.


## Challenges
* Some websites block automated requests with scrapers via web-application firewalls (WAFs) [like Incapsula](https://scrapfly.io/blog/how-to-bypass-imperva-incapsula-anti-scraping/). There are a variety of similar services like Incapsula that vendors are using to protect their sites. A giveaway that a site is using Incapsula is that is has the following cookies (or similar cookies for other services):
    * [visid_incap](https://www.cookie.is/visid_incap_)
    * [incap_ses_](https://www.cookie.is/incap_ses_)

* Some sites may reject a request submitted over a VPN
* Manual intervention is required for sites that are blocked or return irregular/unexpected results
* I did not try to bypass any sites that blocked a request for whatever reason