---
title: "Privacy is a privilege"
date: "2025-01-09"
description: "A look at some obstacles to ensuring privacy as a fundamental human right."
tags:
  - privacy
  - social
ShowToc: true
weight: 1
---


## Introduction
Most in this space are rightly quick to call privacy a ["fundamental human right"](https://www.ohchr.org/en/stories/2013/10/right-privacy-digital-age). As a [TheLaw.Institute article](https://thelaw.institute/privacy-and-data-protection/privacy-fundamental-human-right/) discusses, the right to "privacy" has been recognized by international human rights treaties and guaranteed by international constitutions. 

Yet, many that recognize privacy as a human right will likely also concede that we haven't yet crossed the finish line in effecting it:

* *Politically*, a significant portion of the global population is not covered by some form of privacy legislation, or is only protected by outdated and inadequate laws
* *Socially*, some people lack the technical literacy required to understand the consequences of privacy-impacting decisions they make
* *Culturally*, societal norms may affect the ability of one to make decisions that preserve their privacy, or enjoy the benefits of relevant legal protections
* *Technologically*, assurances are to safeguard privacy are constantly being developed and refined (such as these [awesome open source privacy engineering tools](https://coreyst.one/posts/awesome-opensource-privacyengineering/)),
but organizations are hesitant (or even unequipped) to adopt them while legislators are slow to compel them to do so

With that said, I believe privacy is a human right. I also believe that it's disingenuous to not recognize it is currently a privilege.

[The Britannica Dictionary](https://www.britannica.com/dictionary/privilege) defines "privilege" as:

> privilege (n): a right or benefit that is given to some people and not to others

Privacy is a right *and* benefit not currently universally available to or enjoyed by everyone, and in the rest of this article I'll discuss some of the factors that I believe contribute to this.


## Defining privacy
But first: what even is "privacy"? It depends on who you ask. We can start by clarifying what it is *not*: the mere act of hiding information from someone or something, akin to the common ["nothing to hide argument"](https://en.wikipedia.org/wiki/Nothing_to_hide_argument).

Privacy is vague: it can mean different things to different people, socieities, and governments. Defining it goes way beyond the scope of this post, and really smart people have already done a way better job at it than I could. Professor [Adam Moore](https://faculty.washington.edu/moore2/moore.htm) spends over 15 pages doing so in [Defining Privacy](https://faculty.washington.edu/moore2/DP.pdf). I like to think of privacy as your ability to control what information you share with others. "Others" in this case can be people, companies, governments, your social media page, etc.; this sharing could be an active decision you make, or be the collection of your information by someone else.

As R. Jason Cronk astutely notes in his blog post [A Privacy Engineer’s Thoughts on Criticism of the Solove Taxonomy](https://privacymaverick.com/a-privacy-engineers-thoughts-on-criticism-of-the-solove-taxonomy/), privacy is "philosophical construct" before a legal, political, or technical one, making prescriptive action to effect and defend this right a significant challenge. 

## Obstacles
### Tech literacy
In the [words of Neitzche](https://www.goodreads.com/quotes/331586-but-the-worst-enemy-you-can-meet-will-always-be): *"the worst enemy you can meet will always be yourself"*. This is especially true with regards to privacy, where we are constantly making decisions-- conscious and inconscious-- to share or withold information from others.

Something that influences how we make those decisions is our understanding of the technologies we use and how they affect us, which we can call "tech literacy". 
Generally speaking, tech literacy can be something as simple as knowing how to: send an email, share a .gif with a group chat, or download a mobile app.
In the context of privacy, we are frequently presented with challenges to this literacy as we use technology which often results in the (needless and neglegibly beneficial) disclosure of our personal information:

* Clicking on the "Accept All" button in cookie banners (when the option to block non-necessary trackers exists)
* Checking the optional box to consent to marketing when signing up for something  
* Accepting additional diagnostics or data sharing with third parties (when the option to opt-out exists)
* Not using built-in privacy tools or settings (such as certain account settings, or browser-level protections)
* Not using external, third-party software or tools (such as adblockers, VPNs, private web browsers, etc.)

{{< figure align=left src="/images/firefox-strict-settings.png" >}}
*Firefox's Privacy & Security settings page*

These are all common instances where an individual might unknowingly fail to protect their privacy, possibly because they are not aware of the consequences of their decisions,
or because they just don't know they have a choice to begin with.

Of course - privacy is all about tradeoffs. We sacrifice our privacy for convenience all the time, and I would be a huge hypocrite to rebuke anyone that does so.

However, there are also people who just "don't care" about their privacy, and they are well within their rights to do so. However, I believe that much of this indifference
ultimately stems from technological illiteracy, whether these people would admit it or not.

As a result of tech illiteracy, people:
* Are more likely to give away data when they dont understand the consequences of doing so
* May not be familiar with how to use privacy settings in an app, or even what rights are available to them
* May also not be familiar with tools or things they can use to protect themselves

If our greatest threat to our privacy is indeed ourselves, then no amount of technological or legislative measures to preserve our privacy will solve the root of the issue.
I think a great first step is working to better educate ourselves, and those less technologically-inclined users, about the consequences of our actions as they pertain to our privacy.


### Social economics
A lack of technical literacy is a real issue, but it is not the only issue, nor is it an excuse to victim blame or ignore invasive privacy violations and government or corporate surveillance.

It is also important to look beyond this literacy at face value and instead look at the *why*: why are things this way, and who is predominately affected?

The [National Skills Coalition](https://nationalskillscoalition.org/) does exactly this in [Applying a racial equity lens to digital literacy](https://nationalskillscoalition.org/wp-content/uploads/2020/12/Digital-Skills-Racial-Equity-Final.pdf), where they examine the "digital literacy" of American workers, noting that "workers of color are disproportionately affected by digital skill
gaps compared to their white peers, in large part due to structural
factors that are the product of longstanding inequities in American
society, such as income and wealth gaps and uneven access to
high-quality K-12 education." 

In other words, [socioeconomic factors](https://www.investopedia.com/terms/s/social-economics.asp) directly affect our technical literacy, in the exact same way that they [affect reading literacy](https://sites.lsa.umich.edu/mje/2023/01/05/the-relationship-between-socioeconomic-status-and-literacy-how-literacy-is-influenced-by-and-influences-ses/), where "higher income [is] linked to higher literacy."

They also affect the options that people have with regards to privacy-preserving tools they can use. Take instant messaging, for example. WhatsApp is a free end-to-end encrypted messenger with over 2 billion daily active users. It checks a lot of privacy boxes,
but it [still collects user metadata](https://www.techradar.com/computing/cyber-security/whatsapp-encryption-isnt-the-problem-metadata-is). All is well, though, right? What do you have to worry about if Meta can't actually read your messages? 

A [pertintent Tweet](https://x.com/mysk_co/status/1795210609153163374/photo/1) by user [@mysk_co](https://x.com/mysk_co) points out that "user data is not only about messages." The metadata collected by WhatsApp can be used to gather plenty of sensitive information about you like location data (whether explicitly shared by you or inferred by them),
communication and activity patterns, and ultimately use all this to market to you across Meta platforms, or even [provide this information to law enforcement and governments](https://faq.whatsapp.com/808280033839222/) upon request. Here is [WhatsApp's privacy policy](https://www.whatsapp.com/legal/privacy-policy) if you'd like to see for yourself.

A 2021 [Forbes article](https://www.forbes.com/sites/zakdoffman/2021/01/03/whatsapp-beaten-by-apples-new-imessage-update-for-iphone-users/) shows the comparison between Apple's privacy labels for Signal, iMessage, WhatsApp, and Facebook Messenger.

{{< figure align=left src="/images/data-linked-to-you-comparison.webp" >}}
*via [Forbes](https://www.forbes.com/sites/zakdoffman/2021/01/03/whatsapp-beaten-by-apples-new-imessage-update-for-iphone-users/)*

You may ask, what does this have to do with socioeconomic factors? What am I on about if WhatsApp is *free*? Well, the reason that WhatsApp is able to maintain an active end-to-end encrypted platform with 2 billion users is that it is able to monetize it. No, they're not reading your messages, because *they don't need to* in order to use all the other information they already collect for advertising.

Privacy-superior alternatives exist, such as [Signal](https://signal.org/), which collects no metadata except for a phone number, and [has repeatedly proven](https://signal.org/bigbrother/) that it is literally unable to provide subpoenaed information. However, it has a problem: it is not financially sustainable at a competing scale because it has no data to monetize. Additionally, Signal is a [non-profit](https://signalfoundation.org/en/) and relies entirely on donations and charity.

> Signal still knows nothing about you, but the government still continues to ask us if we do.

A November 2023 blog post by Signal titled [*"Privacy is Priceless, but Signal is Expensive"*](https://signal.org/blog/signal-is-expensive/) reveals that infrastructure costs for the platform are at over 14 million dollars a year. This is for a free service with 40 million users as of 2022 (source?) against WhatsApp's [2 billion](https://www.statista.com/statistics/258749/most-popular-global-mobile-messenger-apps/). Clearly, this model, while supremely private and respectful to the user, 
could not operate in the real world with a much larger user base. This means that a hypothetically much more popular Signal would be forced to switch to a paid model to offset its costs. As nice as it would be for
the whole world to use Signal, reality makes this just a pipe dream for now.

Although I personally would pay for Signal in a heartbeat (and have already donated), that is exactly the point I am trying to make: not everyone is able to make sacrifices for their privacy, finacial or otherwise. Looking at WhatsApp's [market penetration by country](https://www.verint.com/blog/what-countries-are-the-biggest-whatsapp-users/), populations across the world are heavily dependent on the service, and many of these populations with low GDP per capita, such as Kenya, where 97% of people are WhatsApp users, would struggle to find alternative services with a modicum of privacy if WhatsApp were to switch to a paid model.

Ultimately, users would just move on to the next best thing that works, because most don't have the privilege of having the time or money to worry about their privacy. And with modern business models, when people don't have the means to pay for something, they pay with their personal information. 

Am I saying that the people who rely on WhatsApp should stop using it for the sake of their privacy? *Of course not*. It is still offers E2EE messaging, which is extremely important. Giving 2 billion people E2EE messaging is *good*. I use WhatsApp occasionally. But it needs to be recognized that some people don't have the choice to use anything else, and that constitutes a privilege. This is the case for WhatsApp, and it's the case for so much of our technology today, where nothing is ever *really* free.

This can be seen in lots of low-cost hardware and freeware (note: *[not FOSS](https://www.lifewire.com/freeware-definition-4154271)*) where the business model usually revolves around taking an initial loss for the sake of customer acquisition, and later recouping revenue with shady strategies like advertising.
* Low-cost media boxes like [Roku](https://www.fool.com/investing/2023/12/24/roku-hopes-youll-buy-a-shiny-new-roku-smart-tv-thi/) that deliver ["sneaky ads"](https://www.trustedreviews.com/news/roku-learns-sneaky-way-to-show-tv-ads-and-we-hate-the-idea-4514809), while [making it increasingly difficult](https://www.nytimes.com/2024/03/20/technology/personaltech/roku-data-breach-companies.html) to own your device
* Affordable Chinese Android devices that are ["packed with spyware"](https://gizmodo.com/android-xiamoi-oneplus-phones-personal-info-study-1850082989)
* "Free" VPNs that [sell your browsing data and inject ads](https://nordvpn.com/blog/free-vpn-vs-paid-vpn/)

It really goes back to the adage: *if you're not paying for a product,* [*then you are the product*](https://www.forbes.com/sites/marketshare/2012/03/05/if-youre-not-paying-for-it-you-become-the-product/).

> If you're not paying for a product, then you are the product.

Privacy requires time and sometimes money, something lots of people do not have. It is a privilege to consider this, let alone be aware of it. People need money to feed themselves and their families before they
can start worrying about a corporation building an advertising profile of them. Obviously different threat models and [privacy harms](https://coreyst.one/posts/privacy-harms/) exist, but this is just an example.
This harkens back to Maslow's *hierarchy of needs*, where I would place privacy within "self-esteem". The idea of [different Maslow need levels for privacy](https://www.privateinternetaccess.com/blog/understanding-the-different-maslow-need-levels-for-privacy/) definitely merits more attention in the future.

{{< figure align=left src="/images/maslows-hierarchy.jpg" >}}
*via [vectorstock.com](https://vectorstock.com/)*

Something else: [technology is biased](https://www.weforum.org/stories/2021/07/ai-machine-learning-bias-discrimination/). Artificial intelligence suffers from the very biases of its creators, which results in flawed systems like facial recognition that ["victimizes people of color"](https://www.latimes.com/opinion/story/2022-09-29/facial-recognition-technology).

This is the focus of 2020 documentary [*Coded Bias*](https://www.nytimes.com/2020/11/11/movies/coded-bias-review.html), which "explores how machine-learning algorithms can perpetuate society’s existing class-, race- and gender-based inequities."

One subplot in the documentary looks at a low-income, predominantly black housing complex in Brooklyn, where owners deployed facial recognition scanners to building entrances to supplement existing lock-and-key access. Residents express concerns that they feel like guinea pigs for an already discriminatory technology that is not in use in other wealthier housing complexes or apartments in the area. In the documentary Professor Virginia Eubanks quotes that "the future is already here, it's just not evenly distributed", describing this as a predatory trend where punitive and invasive surveillance technologies are first introduced into poor, working-class communities where there are fewer expectations to meet legal resistance or scrutiny.

This even extends to the prison system, as described by the paper [Privacy violations and procedural justice in the United States prisons and jails](https://compass.onlinelibrary.wiley.com/doi/abs/10.1111/soc4.12847), which describes a deficit in privacy protections for incarcerated individuals. They note that "although it is expected that incarcerated individuals have fewer privacy rights than nonincarcerated citizens, some privacy violations may be perceived as procedurally unjust due to their severity and infringement upon incarcerated individuals' rights to dignity and respect." This is further explored by a 2024 paper by Stephen Raher who describes modern carceral settings as the ["digital panopticon \[returning\] to its roots"](https://northwesternlawreview.org/articles/data-privacy-in-carceral-settings-the-digital-panopticon-returns-to-its-roots/).


### Geographic jurisdictions
According to the IAPP's [Global Privacy Law and DPA Directory](https://iapp.org/resources/global-privacy-directory/), as of March 2024, over 137 countries, or 70% of all nations, have national data privacy laws. A complementary [IAPP article](https://iapp.org/news/a/identifying-global-privacy-laws-relevant-dpas/) reads that "79.3% of the world's population is covered by some form of national data privacy law". 

That's great, and those numbers are growing year by year. But don't let it distract you from the reality that there are still people who *aren't* protected by these guarantees. 
There are also cases where these laws might provide different, or weaker, protections than legislation of other states or nations. 

The US's state-based approach is a token example, as the IAPP's [US State Privacy Legislation Tracker](https://iapp.org/resources/article/us-state-privacy-legislation-tracker/)
illustrates, where independent states develop their own privacy regulations which afford rights to their citizens which those of another state might not enjoy. For example,  
California is currently the only state that affords citizens the right to a private right of action in certain cases. Someone from Kentucky may have the right to opt in for sensitive data processing, but not in Iowa. A resident of Virginia can reject to a company using automated decision-making, but not Utah.

Take a look at the IAPP's [US State Comprehensive Privacy Laws Report](https://iapp.org/resources/article/us-state-privacy-laws-overview/). Only 19 states have any comprehensive protections to begin with. This problem is not exclusive to the US, as a remaining 30% of nations still lack any comprehensive protections. 

{{< figure align=left src="/images/iapp-state-tracker-jan2025.png" >}}
*via [IAPP](https://iapp.org/resources/article/us-state-privacy-legislation-tracker/)*


### Corporate influence
Personal data has value: to the data subjects it belongs to, but even more so to the companies collecting it. 
Companies know this value, because they have been [measuring it](https://showmethedata.blog/how-to-measure-the-value-of-data) for years. This value drives corporations to collect
as much [high-quality data](https://www.ibm.com/products/tutorials/6-pillars-of-data-quality-and-how-to-improve-your-data) as they can, through whatever means necessary. 

One of the ways they can do this is by by offering some sort of financial incentive to consumers at the cost of their personal information. 
This practice is actually very common today and most people have likely participated in one or more of these incentives. The business usually solicits some amount of personal information, 
like a name, phone number, and/or email address, in exchange for something of "value". 

In the marketing industry, this is simply known as ["incentive marketing"](https://www.tremendous.com/blog/what-is-incentive-marketing/) and it's a (gross) popular tactic to increase customer retention and spending.
According to a martech company, here are some common examples that ["customers can't resist"](https://www.kennect.io/post/incentive-marketing#6-marketing-incentives-customers-cant-resist): 
* Referral bonuses
* Discounts and coupons
* Free trials and samples
* Loyalty programs
* Contests and giveaways
* Early access

{{< figure align=left src="/images/incentive-marketing.png" >}}
*via [kennect.io](https://www.kennect.io/post/incentive-marketing)*

Aside: I emphasized the quotes around *value* because this value is really in the hands of the business. There is a reason they offer you these incentives,
and it's because it makes them more money. They wouldn't do it if it was losing them money.
I do not participate in these incentives because I do not appreciate corporations that [manipulate psychology](https://blog.growthpanels.com/why-loyalty-programs-work-the-psychology-behind-reward-schemes/) to try to take my money.

This incentivization is actually expressly allowed by the [California Consumer Privacy Protection Act](https://www.oag.ca.gov/privacy/ccpa) and some other comprehensive state regulations across the US.
The CCPA tucks this into the [*right to non-discrimination*](https://www.kelleydrye.com/viewpoints/blogs/ad-law-access/the-ccpa-non-discrimination-right-explained), which means that "businesses cannot deny goods or services, charge you a different price, or provide a different level or 
quality of goods or services just because you exercised your rights under the CCPA."

However, remember how personal data has value? The CCPA recognizes this, and even provides [guidelines for calculating that value](https://www.privacysecurityacademy.com/wp-content/uploads/2019/10/Third-Parties-and-the-CCPA.pdf) so that businesses can "offer you promotions,
discounts and other deals in exchange for collecting, keeping, or selling your personal information. 
But they can only do this if the financial incentive offered is reasonably related to the value of your personal information." 

This is not to bash on the [CPPA](https://cppa.ca.gov/) or demonize the CCPA. California has historically been the most progresive state for consumer privacy in the nation. Yet, regardless of what you think about this practice, you cannot deny that these incentives create an inherent imbalance that might hook  some individuals, like a poor single mother, for example, and not others purely for economic reasons.  Although these incentives are *available* to everyone, they might only be *interesting* or *appealing* to those in challenging financial situations. And that imbalance predicates privilege. 


### Cultural attitudes 
We are all human, but our culture significantly influences our thoughts and behaviors.
This influence extends to our perceptions of privacy and our willingness to share our personal information with people, companies, and the internet at large.

In [The Role of Gender, Age and Cultural Differences in Online Information Disclosure and Privacy: A Systematic Review](https://link.springer.com/chapter/10.1007/978-3-031-09070-7_61?fromPaywallRec=false), William Malatji demonstrates "clear relationships between cultural variables and self-disclosure choices", affirming that "culture was found to be one of the influential factors towards users’ information disclosure behaviour in online platforms." Essentially, you may be more willing to share details about your personal life on the internet, depending on your culture.

A 2022 paper titled [Cultural Influences on Personal Data Disclosure Decisions](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4068964) by Lena Kessel investigates various sociocultural beliefs about privacy. The study, while focused specifically on participants in the 
United States, examines some of the following ideas about privacy that may impact how it is perceived, practiced, or legislated in any society:
* The trustworthiness of other people
* The general value of informational privacy
* Perceptions of workplace and governmental surveillance
* Trust in businesses and institutions
* Benefits associated with data disclosure

{{< figure align=left src="/images/data-sharing-risk.png" >}}
*via [Cultural Influences on Personal Data Disclosure Decisions](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4068964)*

In [The Anthropology of Privacy How Cultural Shifts Are Reshaping Data Protection Policies](https://judgmentcallpodcast.com/2024/08/the-anthropology-of-privacy-how-cultural-shifts-are-reshaping-data-protection-policies/), the author discusses
how cultural norms reflect in the public perception and legislation around data privacy, and goes into much more detail than I can for this post. However, I have to note that this article provides 
zero sources anywhere, and one could assume that it was generated by AI, but I still think it makes for an excellent thought experiment.

For example, the author considers the differences between collectivist and individualistic cultures and how they perceive privacy. The article reads: "individuals from collectivist cultures, such as those in East Asia, tend to have a lower expectation of digital privacy compared to those from more individualistic societies in the West."

This is supported by Malatji's study, who writes that "collectivism relating to society and power distancing influence the strength of the association between privacy concerns and surveillance acceptance significantly, as well as the adoption of privacy protections." 

In a similar study, [Cross-Cultural Privacy Differences](https://link.springer.com/chapter/10.1007/978-3-030-82786-1_12) by Yao Li, Li dives deep into these cross-cultural differences, comparing participants from various "individualistic" countries like the US, Australia, Germany, et. al, and "collectivistic" countries like India and China.

Privacy perceptions can also be influenced by the role technology plays in a society. Where a society readily embraces technological innovation, individuals might be more willing to share their
personal information, often to enjoy the resulting conveniences and benefits afforded by this technology. However, for less technologically advanced societies, the opposite might be true.

This can be seen in 2021 [DW](https://www.dw.com/) documentary [*China - Surveillance state or way of the future?*](https://www.youtube.com/watch?v=7gSU_Xes3GQ), which explores 
China's technological advancements (specifically, in facial recognition), government surveillance, social credit system, and its public's perception of all of this less than two years into the COVID-19 pandemic.

{{< youtube id="7gSU_Xes3GQ" image="/youtube/dw-china-documentary-thumbnail.jpg" >}}

We see how deeply engrained technology is into the lives of everyday people in China, so much so that it is possible to pay for a taxi or buy a snack only with a biometric facial scan.
The documentary shares the story of Deng Yufeng, a Chinese artist who created a ["performance art project"](https://www.sixthtone.com/news/1006432) featuring a video of people comically trying to walk around the streets of Beijing without being recorded by a vast network of public cameras. For any Monty Python fans, it is like a Chinese homage to the [Ministry of Silly Walks](https://www.youtube.com/watch?v=iV2ViNJFZC8). The project was intended to highlight the "country's rapidly expanding surveillance network", but was promptly censored by the Chinese government, who ordered Yufeng to cease distribution of the video.

Yufeng, curiously, however, goes on to express support for China's proliferating data collection and surveillance practices, specifically to combat the pandemic, claiming that it is an "ethical tradeoff" that he is willing to make for technology that offers to save lives. "Is privacy or human life more important? [...] In this case, I think everyone makes the decision that life is more important."

> Is privacy or human life more important?

A completely valid point, but not the topic for this post. My point is that someone in a collectivistic society that might be more privacy-conscious, preferring not to transact with or participate in social programs like these, might literally not have the choice. What happens when vendors stop accepting cash? Or when we have to scan our faces to enter the subway? Again, any social merit that might result from these technologies does not invalidate the imbalance that it creates.