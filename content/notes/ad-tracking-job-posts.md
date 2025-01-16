---
title: "Ad tracking in job postings"
date: "2025-01-15"
ShowToc: false
ShowReadingTime: true
description: " "
---

Of all the problems I expected to run into during my job search,
this was not one of them.

And I feel like I shouldn't even be surprised anymore.

{{< figure align=left src="/images/citi-linkedin-post.png" >}}
 
I was recently looking through job postings on LinkedIn and clicked on a posting by your [friendly](https://violationtracker.goodjobsfirst.org/parent/citigroup) [neighborhood](https://www.reuters.com/business/finance/us-bank-regulators-fine-citi-136-million-failing-address-longstanding-data-2024-07-10/) Citi Bank (not the role in the screenshot above).

My browser (more specifically, my ad/tracker-blocker browser extension [uBlock Origin](https://ublockorigin.com/)) stopped me from visiting the page and warned me that the link I had clicked on was being redirected through `ad.doubleclick.net`: an ad network managed by Google. 

{{< figure align=left src="/images/ublock-warning-linkedin.png" >}}

Straight from the horse's mouth, [Google describes](https://support.google.com/faqs/answer/2727482?hl=en) DoubleClick as "an integrated ad technology platform that enables advertisers to more effectively create, manage and grow high-impact digital marketing campaigns." 
A [Strategy Story article](https://thestrategystory.com/2020/12/14/google-doubleclick-acquisition/) claims that Google Ads "is what it is today because of the acquisition of [DoubleClick]" after the [FTC approved the merger](https://www.ftc.gov/news-events/news/press-releases/2007/12/federal-trade-commission-closes-googledoubleclick-investigation) in 2007.
Basically companies use DoubleClick to advertise their products on the platform, and DoubleClick delivers these ads based on a user's browsing history. 
A 2016 [Wired article](https://www.wired.com/story/google-ad-tracking/) describes why this is concerning.

As you can see in the report provided by uBlock, Citi has created an ad campaign for their job postings, represented by the `utm` arguments. "UTM" stands for [Urchin Tracking Module](https://en.wikipedia.org/wiki/UTM_parameters)-- the name alone sounds sinister-- which are "URL parameters used by marketers to track the effectiveness of online marketing campaigns."

*But would someone really create a targeted ad campaign for job applicants? Who would do such a thing?* 

Citi would. And does. They say so in the [Cookie Privacy Notice](https://careers.citigroup.com/cookies/) on their Careers page:
> EXTERNAL COOKIES FROM SERVICE PROVIDERS AND SELECTED PARTNERS
> 
> **For Marketing and Behavioral Advertising Purposes**
>
> Advertising platforms such as Google Marketing®, Google AdSense, Google AdWords, DoubleClick and Customer Match data; and user trackers from social media channels such as Facebook, LinkedIn, Twitter and YouTube, help us deliver multimedia content which may be relevant to visitors through their interactions with our sites, and track responses to advertising to measure the effectiveness of Citi’s online campaigns. Information captured typically includes web requests, session ID, browser types, browser languages and/or the date and time of visitor interaction with Ads.
> 
> **Foreign Signals Intelligence**
>
> Google Analytics, the Google Marketing Platform and YouTube are brands of Google, Inc., Twitter is a brand of Twitter, Inc., and Facebook is a brand of Meta Inc. All are U.S. electronic communications services providers subject to the CLOUD Act (18 USC § 2523), the Foreign Intelligence Surveillance Act (50 USC 36 §1801) and Executive Order 12333 (each as restated and amended). These statutes allow federal law enforcement and intelligence agencies, under strict conditions, to request from service providers and partners, browsing and technical data of foreign individuals where their data is transferred to, or accessed from, the United States.
> 
> You may use our cookie preferences tool or adjust your browser settings to decline or deactivate Functional, Analytics, Marketing or Behavioral Advertising cookies. You may also use the online tools to select cookies and trackers individually as described below.

But you have a choice!

{{< figure align=left src="/images/citi-careers-privacy-policy.png" >}}

So there it is. "Marketing and Behavioral Advertising Cookies" are what the layperson knows to be "trackers" or "targeted ads".
Top that off with Google Analytics, which is already [problematic for privacy](https://matomo.org/blog/2022/06/google-analytics-privacy-issues/),
and you have a company using marketing tools to learn about job applicants.


Switching platforms to Indeed is a little different in this case: I could only find one post that yielded this tracker- all other posts directed to Citi's career page without issue.
The uBlock report shows a new UTM campaign that I didn't see with LinkedIn: `utm_campaign = 2024 global technology - nam - us - multimarket - fraud analytics`. The `utm_source` is also tied to Indeed. So they even have different campaigns for different postings.

{{< figure align=left src="/images/ublock-warning-indeed.png" >}}

This is not to single-out Citi. They were just the first company I noticed doing this during my job search. Since then, I've learned that they're not the only one. 
I also found Applied Materials to be doing the same thing on LinkedIn, (ironically?) for a "Technical Program Manager - Analyst, Privacy and Data Governance" opening.

{{< figure align=left src="/images/ublock-warning-appliedmaterials.png" >}}

And yet their [Candidate Privacy Policy](https://www.appliedmaterials.com/us/en/pages/candidate-privacy-policy.html) claims they "process only technically necessary cookies to assure the Career Portal is working as intended or that are essential for your user experience." 
This policy makes me unsure if that is really the case here, as I can see DoubleClick and Google Analytics loading into my browser,
which are in no way "essential".

{{< figure align=left src="/images/appliedmaterials-tracking-cookies.png" >}}
Google defines these [advertising and "measurement" (analytics) cookies](https://business.safety.google/adscookies/), which include
`FLC` and `IDE`.

If there is some technical detail I'm missing or not understanding here for Citi or Applied Materials, please let me know. I *want* to be proven wrong in this case.
And I'll gladly edit this post if so.

Regardless, this practice in general is just gross and exploitative. Even if a company provides a popup banner to reject/opt-out of this tracking, *why is the tracking there in the first place?*

There are currently 1,932 results for job postings by Citi on LinkedIn, and the dozen I tested have this tracker.
Many of these posts show "over 100 people clicked apply". 
Excluding any posts that use Easy Apply (for applying directly through LinkedIn), it's easy to imagine that there are thousands of applicants having their data harvested this way.

Job hunting is already difficult enough. Applicants can feel tired, anxious, desperate, or with no alternative, 
and a cookie banner popping up while trying to apply for a job only exacerbates and, I argue, exploits that mental burden to enable data collection about applicants- which
doesn't even tangibly benefit them.


If you haven't already, do yourself a favor and install [uBlock Origin](https://ublockorigin.com/) to get rid of annoying ads across the internet and protect yourself against invasive and concealed tracking like this. Use a [privacy-respecting](https://www.zdnet.com/article/best-browser-for-privacy/) web browser.
Fight back against internet [enshittification](https://www.cnn.com/2025/01/13/business/enshittification-internet-meta-nightcap/index.html).