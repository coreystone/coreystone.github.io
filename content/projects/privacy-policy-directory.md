---
title: "Privacy Policy Directory"
date: ""
description: "An organized collection of privacy policies for some of the top F500 companies and data brokers."
ShowToc: true
---

* Read more about the web scraper complementing this project: [click here](https://coreyst.one/projects/privacy-policy-scraper/)

## About
**Privacy Policy Directory** is an organized collection of 528 companies that serves to educate the public about how it  can exercise their privacy rights with any of these companies that they might be a user of.

This project was heavily inspired by and modeled on [2fa.directory](https://2fa.directory/) whose mission is *"to be an independent source of information on which services support MFA/2FA and help consumers demand MFA/2FA on the services that currently don’t."* I've always admired how the project presents its data and its utility to the public. I noticed an equivalent was missing in the privacy space and what you see here is my attempt at the humble beginning. 

Trying to exercise your privacy rights (such as to access or delete your data) can unfortunately be a pain solely because you have to become a detective to find an email address or obfuscated link hidden away in some corner of a company's website. I've noticed this pattern too often in my experience. This project serves to save data subjects that headache and time sink of finding *where* to submit a request rather than the trivial act of submitting it. When people feel more confident in exercising their privacy rights, people win and privacy prevails.


## Disclaimer
This project is built on top of publicly available information that is provided by companies and their privacy policies, support articles, or other sources of information found on their websites. *Sounds a lot like what data brokers say, doesn't it?* 

However, there is no guarantee that all of the information presented here is correct. This project is intended to be a reference point and not a definitive or absolute source of truth. Companies update their privacy policies, links, and other processes for data requests constantly, so data presented here can change or become stale/invalid at any time. That said, I did my best to try to make everything as accurate as I could.


## What is included?
* **Privacy Policy**: a hyperlink to a company's privacy policy (sometimes called privacy "notice" or "statement")
* **Contact**: an email address to contact that can help fulfill a privacy request; usually a company's privacy department (`privacy@example.com`), data protection officer (`dpo@example.com`), or support team (`support@example.com`)
* **Request Form**: a hyperlink to a form or mechanism where you can directly submit a request; these can be internal to a company or be provided by a third-party solution, such as a [OneTrust privacy webform](https://www.onetrust.com/products/privacy-rights-automation/)
* **Request Type**: classifies the mechanism a company provides to its users to submit a request
     * Email, internal form, account settings, third-party webform (OneTrust, Truyo, Securiti, TrustArc, LogicManager, et. al), phone number, etc.
* **Privacy frameworks**: indicates whether a privacy policy explicitly mentions a U.S. states's privacy law or that citizens of a specific state have special rights
     * [California Consumer Privacy Act/California Privacy Rights Act (CCPA/CPRA)](https://www.oag.ca.gov/privacy/ccpa)
     * [Colorado Privacy Act (CPA)](https://coag.gov/resources/colorado-privacy-act/)
     * [Connecticut Data Privacy Act (CTDPA)](https://portal.ct.gov/AG/Sections/Privacy/The-Connecticut-Data-Privacy-Act)
     * [Nevada SB 220](https://www.leg.state.nv.us/App/NELIS/REL/80th2019/Bill/6365/Text)
     * [Texas Data Privacy and Security Act (TDPSA)](https://www.osano.com/articles/texas-data-privacy-and-security-act-tdpsa)
     * [Virginia Consumer Data Protection Act (VCDPA)](https://law.lis.virginia.gov/vacode/title59.1/chapter53/)
     * [Utah Consumer Privacy Act (UCPA)](https://dcp.utah.gov/ucpa/)
* **CCPA Metrics**: a link to the company's [CCPA metrics report](https://www.onetrust.com/blog/ccpa-metric-reporting-requirement/) if applicable, per  Section 999.317(g) of the CCPA'


## Analysis
Almost 70% of companies make explicit mention of the CCPA, or that California residents have special rights over their data. Other states are not so frequent, but I imagine these numbers will climb significantly as the dates get closer 
to these other state laws coming into effect.
{{< include-html "/static/ppd-bar.html" >}}


OneTrust far and away has the majority of the market here, but over 30% of companies still provide their own custom form or solution for responding to privacy requests, and 22% simply use email.
{{< include-html "/static/ppd-pie.html" >}}
