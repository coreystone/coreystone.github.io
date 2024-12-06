---
title: "GPC/DNT signal checker"
date: ""
description: "A simple tool to check if sites using the OneTrust CMP respect GPC/DNT signals."
ShowToc: true
---

## About
This project scrapes a website that has implemented the OneTrust and OneTrust's CookiePro [consent management platform (CMP)](https://www.onetrust.com/cookiepro/) to identify if the site honors a Do Not Track or Global Privacy Control signals from a site visitor. It will also list all categories of cookies used by the site and each cookie within a category.

A brief overview:
* [Global Privacy Control (GPC)](https://globalprivacycontrol.org/) is a browser-level opt-out signal that communicates to a web server that the visitor does want the company to sell or share their personal information
  * This is an officially recognized mechanism to submit an opt-out request under the [CCPA §999.315](https://www.oag.ca.gov/sites/all/files/agweb/pdfs/privacy/oal-sub-final-text-of-regs.pdf) 
  * It is also intended to "convey a general request that data controllers limit the sale or sharing of the user’s personal data to other data controllers" per [Articles 7 & 21 of the GDPR](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32016R0679)
* [Do Not Track (DNT)](https://en.wikipedia.org/wiki/Do_Not_Track) is the neglected predecessor of GPC that everyone seems to be trying to forget about. Companies are not legally obligated to honor DNT and most explicitly state that they don't in their privacy policies.

* For a more in-depth comparison of the two, check out this [article by Clarip](https://www.clarip.com/data-privacy/what-is-global-privacy-control-and-why-does-it-matter/).


## How it works
OneTrust offers cookie banners and preference centers that a site visitor can interact with to indicate their cookie consent preferences. It also offers companies the option to notify visitors when a GPC or DNT signal has been detected and will be honored, although, in my experience, this is not commonly used. Though OneTrust can respond to both GPC and DNT, it does not specify which signal it is responding to by default.

{{< figure align=left src="/images/cruise-pc.png" >}}
*The [Cruise](https://getcruise.com/) cookie preference center*

The OneTrust CMP is created by a JavaScript file called `otSDKStub.js` that is placed into the header of a site's HTML source code, which is what displays the cookie banner and/or preference center across the site. This file will be important later.

``` html
<!doctype html>
<html lang="en">
  <head>
    <title>Website name</title>
    <script type="text/javascript" src="https://cdn.cookielaw.org/consent/xxxx-xxxx-xxxx-xxxx/OtAutoBlock.js"></script>
    <script src="https://cdn.cookielaw.org/scripttemplates/otSDKStub.js" type="text/javascript" charset="UTF-8" data-domain-script="xxxx-xxxx-xxxx-xxxx-xxxx"></script>
    <script type="text/javascript">
      function OptanonWrapper() {}
    </script>
```

Note: The [cookielaw.org](https://www.cookielaw.org/) and [cookiepedia.co.uk](https://cookiepedia.co.uk/eu-cookie-law) domains are owned by OneTrust.

I fetch the website using the `requests` library and load the JSON from the page.

``` python
response = requests.get('https://www.chick-fil-a.com/')
data = json.load(f)
```

Because that that JavaScript file is present at the top of the HTML \<head\> section, we can conveniently get what we need from the first grouping in our JSON object.

`DomainData` is a top-level group that stores all the info for the CMP implementation.
Within it, we can see an array called `Groups` that contains each cookie category as it appears in the preference center, like "Strictly Necessary Cookies", "Analytics Cookies", and the rest.
``` json
{
  "DomainData": {
    ...
    "Groups": [
      {
        "Order": "1",
        "OptanonGroupId": "C0001",
        ...
        "GroupDescription": "These cookies are necessary for the website to function and cannot be switched off in our systems. They are usually only set in response to actions made by you which amount to a request for services, such as setting your privacy preferences, logging in or filling in forms. You can set your browser to block or alert you about these cookies, but some parts of the site will not then work. These cookies do not store any personally identifiable information.",
        "GroupName": "Strictly Necessary Cookies",
        "FirstPartyCookies": [
          {
            "id": "3593911a-9bd2-4140-9d9c-a50fc68362bd",
            "Name": "OptanonAlertBoxClosed",
            "Host": ".example.com",
            "IsSession": false,
            "Length": "365",
            "description": "This cookie is set by websites using certain versions of the cookie law compliance solution from OneTrust.  It is set after visitors have seen a cookie information notice and in some cases only when they actively close the notice down.  It enables the website not to show the message more than once to a user.  The cookie has a one year lifespan and contains no personal information.",
          },         
```


Now its trivial to iterate over each cookie category (group) and get what I'm looking for.

With OneTrust, DNT and GPC signals are assigned per category, not per cookie, which means the value will be found within the the Group.

``` json
"IsDntEnabled": false,
"IsGpcEnabled": true
```
 
Iterate over each cookie in a Group to view all cookies in a category. I'm interested in the cookie's:
* `Name`: the name of the cookie (eg, "_ga" for Google Analytics)
* `id`: the unique identifier of the cookie (eg, "_ga_xxxxxxxxx")
* `Host`: the domain hosting the cookie (eg, ".example.com")
* `Session`: indicates whether the cookie is a [Session or Persistent cookie](https://secureprivacy.ai/blog/session-cookies-vs-persistent-cookies)
* `Length`: the duration that the cookie remains in storage, in days
  * Session cookies have a value of 0
  * Persistent cookies have a [max value of 400](https://developer.chrome.com/blog/cookie-max-age-expires/) (about 13 months)
* `description`: a short explanation of what the cookie is/does

This block prints all of the relevant information that OneTrust has about a cookie, which can be automatically pulled from the cookiepedia repo of known existing cookies, or manually configured by the OneTrust admin.
``` python
for group in data['DomainData']['Groups']:
    if len(group['FirstPartyCookies']) == 0: print("No cookies found")
    else:
        for cookie in ['FirstPartyCookies']:
            print(cookie['Name']')
            print(cookie['id'])
            print(cookie['Host']')
            print('Session' if cookie['IsSession'] == 'True' else 'Persistent')
            print(f'Duration (days): {cookie['Length']}')
            print(f'Description: {cookie['description']}')
```


## Limitations
The main limitation of this solution is that it is only compatible with sites using the OneTrust consent management platform (CMP). This could be configured to work with similar CMPs from other vendors like [Ketch](https://www.ketch.com/resources/cookie-consent-banner) and [Osano](https://www.osano.com/cookieconsent), but I just wanted to start with a working prototype first. However, anecdotally, a majority of websites that are using third-party CMPs are using OneTrust or OneTrust's CookiePro (though many customers seem to be ditching OneTrust for its competitors), so this solution has pretty decent coverage. 

Some websites will automatically block the script or try to enforce "human checks" as an anti-bot/anti-scraping measure. Some requests made over VPN will also be rejected as well. I do not try to bypass any sites that don't like these requests.

## Related projects
I found a similar project from Wesleyan University's [Privacy Tech Lab](https://privacytechlab.org/) called [GPC Web Crawler](https://github.com/privacy-tech-lab/gpc-web-crawler) which has a similar goal in identifying which sites honor the Global Privacy Control signal, but is vendor-agnostic and uses automated browser testing (with Selenium) to see if the signal is actually honored or not rather than taking the website's word for it.


Here is how it works, taken from the project's [GitHub repo](https://github.com/privacy-tech-lab/gpc-web-crawler):
>    1. The extension checks whether the site is subject to the CCPA by looking at Firefox's urlClassification object. Requests returned by this object are based on the Disconnect list, as described here.
>    2. The extension checks the value of the US Privacy string, OneTrust’s OptanonConsent cookie, and the GPP string, if any of these exist.
>   3. The extension sends a GPC signal to the site.
>    4. The extension rechecks the value of the US Privacy string, OptanonConsent cookie, and GPP string.

{{< figure align=left src="/images/gpc-web-crawler-flow.png" >}}
*A flow diagram of the web crawler script per the [gpc-web-crawler repo](https://github.com/privacy-tech-lab/gpc-web-crawler)*

This solution is much more technical and has the benefit of not being limited by what CMP a site is using. I also like that this solution searches for other signals like the IAB's [Gloabl Privacy Platform (GPP)](https://github.com/InteractiveAdvertisingBureau/Global-Privacy-Platform/blob/main/Core/Consent%20String%20Specification.md) string and also the [US Privacy string](https://github.com/InteractiveAdvertisingBureau/USPrivacy/blob/master/CCPA/US%20Privacy%20String.md) (although it has recently been deprecated). Though the idea of "signal sprawl" is a good conversation for another day, I do appreciate that there are more and more solutions releasing to effect user consent.