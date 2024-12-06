---
title: "Privacy Poodle"
date: ""
description: "An app that empowers users to send automated data subject request emails to the top data brokers and people search sites."
ShowToc: true
---

## About
**Privacy Poodle** is an application that educates users about their data privacy rights afforded to them by the [CCPA](https://www.oag.ca.gov/privacy/ccpa), [GDPR](https://gdpr.eu/what-is-gdpr/), and [VCDPA](https://pro.bloomberglaw.com/brief/what-is-the-vcdpa/) and empowers users to 
easily exercise these rights by sending *automated* data subject email requests to a hand-picked selection of the top [data brokers](https://surfshark.com/blog/what-is-a-data-broker) and [people search sites](https://consumer.ftc.gov/articles/what-know-about-people-search-sites-sell-your-information) that profit off of our data.

[Wikipedia reads](https://en.wikipedia.org/wiki/Poodle#History) that "[the] modern Poodle's ancestors were widely used by waterfowlers both to retrieve shot game and to recover lost arrows and bolts that had *missed their mark*." 

Privacy Poodle aims to do just that with your data: *discover* and/or *delete* the pieces that have gone astray and ended up in places you never intended or even imagined, ie. in the hands of data brokers, and then instructing those brokers to give you back control over your data.

## Demo
{{< video
  src="/images/privacy-poodle-demo.mp4"
  width="500"
>}}


## 🦴 How it works
A GUI guides you through everything needed to help you understand, configure, and review before submitting requests to a litany of data brokers. 
1. The program asks you for your *region* to select a corresponding privacy framework that will be the basis for the requests and your *name*. Note: A full name and email address are needed to submit a valid data request to companies.
2. Select your email provider (Gmail, Outlook, Proton Mail) and enter login credentials
3. Select the request type: **access** OR **delete + opt-out**
4. Select the list number of companies to send emails to
5. Review the email to be sent and confirm
6. See the CSV report log for all emails sent to companies
7. You follow up with these companies/requests on your own

{{< figure align=left src="/images/demo-screenshots.png" >}}

## Disclaimer
This program was created before the passage of the [California Delete Act](https://iapp.org/news/a/california-governor-signs-ca-delete-act-into-law/) (SB 362), which aims to create a "one-stop-shop mechanism by 1 Jan. 2026 for consumers who are securely verified to request the deletion and tracking of their personal data." 

Although you have the choice, I do NOT recommend submitting blanket requests to data brokers outside of the top 10 or 25 sites. Not only is this a huge time investment, but more importantly it could potentially introduce your data to companies that didn't even have it to begin with. A company that had no record of you would now have a record that you submitted a request with them, including your name, email address, and any other verifying information that you might be asked for.

## Why should you care about data brokers? 
Watch John Oliver's segment about data brokers on Last Week Tonight.
{{< youtube id="wqn3gR1WTcA" image="/youtube/data-brokers-thumbnail.jpg" >}}

## What can you expect?
Watch the video below to see how 600 data brokers responded to deletion requests submitted by [@yoavaviram](https://github.com/yoavaviram) and [@roughprada](https://github.com/roughprada) and the [(dark) patterns](https://www.comparitech.com/blog/information-security/dark-patterns/) they noticed.

{{< youtube id="SY_YAZEJPjc" image="/youtube/dark-patterns-thumbnail.jpg" >}}

## Acknowledgements
* This project was originally inspired by [Privacy Bot](https://github.com/privacybot-berkeley/privacybot), a now deprecated project that also submitted automated email privacy requests for users.
My goal was to firstly revive this project and then expand upon its functionality and make it more accessible.

* [Concious Digital's](https://consciousdigital.org/) stellar initiatives [Data Broker Watch](https://databrokerswatch.org/) and [Own Your Data](https://yourdigitalrights.org/) were also invaluable in contributing to
the [data broker list](https://databrokerswatch.org/top-ten) used by this project and also the verbiage for the email body templates for access and deletion requests. I slightly adapted these templates for the CCPA, VCDPA, and GDPR.
  * This [video presentation](https://www.youtube.com/watch?v=SY_YAZEJPjc) by Conscious Digital from Good Tech Fest 2022 was also inspiring and enlightening
  
* [Red Mail](https://github.com/Miksus/red-mail) for Python was used for all the email-sending functionality. Thank you to @Miksus for the excellent library and documentation.

* All emojis designed by [OpenMoji](https://openmoji.org/) – the open-source emoji and icon project. License: CC BY-SA 4.0

* [Wikimedia]() for the flag images
  * <a href="https://commons.wikimedia.org/wiki/File:Flag_of_California.svg">Original:  Donald Graeme KelleyVectorization:  Devin Cook</a>, Public domain, via Wikimedia Commons
  * <a href="https://commons.wikimedia.org/wiki/File:Flag_of_Europe.svg">User:Verdy p, User:-xfi-, User:Paddu, User:Nightstallion, User:Funakoshi, User:Jeltz, User:Dbenbenn, User:Zscout370</a>, Public domain, via Wikimedia Commons
  * <a href="https://commons.wikimedia.org/wiki/File:Flag_of_Virginia.svg">Commonwealth of Virginia</a>, Public domain, via Wikimedia Commons
