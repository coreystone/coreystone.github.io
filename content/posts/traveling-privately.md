---
title: "Traveling with privacy and security in mind"
date: "2024-12-01"
description: "How to enjoy your travels while protecting your privacy and digital devices."
tags:
  - privacy
  - travel
ShowToc: true
weight: 1
---



## Introduction
I recently returned from a trip abroad in Mexico and it was an incredible time that I plan to write about separately. However, despite all of the preparation and research I had done beforehand, things still always found a way to not go according to plan. Although I would argue that is part of the fun of travel, the element of surprise is still very real. That said, everything that continues will be from the angle of my experiences in Mexico, though these lessons should generally apply to the rest of the world. As with all travel: do your research beforehand based on wherever you're going.

I asked Meta's [Llama 3.1](https://www.llama.com/llama3_1/) to provide an opening statement about the difficulties of preserving your digital privacy while traveling abroad, and I was pretty happy with its response that I'm using to introduce this post:

> Traveling - a time to disconnect from the daily grind and reconnect with the world around us. But in today's digital age, the freedom to roam comes with a hidden cost: our online security and personal data. As we navigate unfamiliar destinations, we often find ourselves making compromises for the sake of convenience, sacrificing our digital privacy in the process. From using public Wi-Fi to access maps and itineraries, to sharing personal details with travel apps and websites, the risks to our digital well-being can be just as real as the rewards of exploring new places.

It's already challenging enough dealing with all of the delays, cancellations, and things that never go according to plan while you're traveling- and this can lead to sacrifices like missing out on certain sights and experiences and compromises like spending too much money on last-minute bookings and transportation. Another sacrifice I've noticed during my travels is that of my digital privacy. On a vacation or business trip, it's easy to lose count of all the times you hand someone your ID or passport, fill in a (paper or digital) form with your name, address, phone number, or email, or even connect to a public Wi-Fi network. It can be really overwhelming to keep track of all of these activities, physical and digital, that accumulate your [digital footprint](https://en.wikipedia.org/wiki/Digital_footprint) and can affect your privacy. So I made a list of these common activities  while traveling and how to approach them in a realistic way that preserves your privacy without having to ruin your trip.

Disclaimer: This post is NOT about going "off the grid" or hiding from a government. If that is what you are trying to do, you're in the wrong place. This post is about balancing the challenges of preserving your privacy and the security of your devices while enjoying your travels.

## The reality of travel
A government rightfully has a vested interest in knowing who and what enters its borders and when. Much like when you step outside of your house into public, [you have no expectation of privacy](https://sandiegoprivacy.org/myth-no-expectation-of-privacy-in-public.html) when stepping into a new country- much less so if you are not a citizen. It's a little more complicated than that, but it I believe it to be true when you're in another country.

Be ready to present identification to government officials (and businesses depending on the activities you have planned), and expect to be subjected to recordings, biometric scanners, and even to potentially have your devices be searched. Like it or not, these are all things that can and do happen at borders (some more than others, of course) and you need to be okay with that before deciding to travel.

Do NOT lie or provide falsified documents to any government with the goal of retaining your privacy. That is a horrible idea.

This blog post is not about hiding from those governments or disappearing. It is about recognizing how your privacy can be negatively affected while traveling and what you can realistically do about it. This includes protecting yourself from companies and public networks, whether incompetent or malicious, while maintaining full functionality of all the digital devices and services you need to go about and enjoy your trip. 
## Establish your threat model
Before doing anything, you need to first ask yourself a few questions to guide yourself through this process. I'm going to provide the basic questions loosely based on those in [this EFF article](https://www.eff.org/keeping-your-site-alive/evaluating-your-threat-model) that help define your "threat model": a framework used to identify, evaluate, and prioritize potential risks to your personal information and online security. This archetype actually [originated in information security](https://www.iriusrisk.com/resources-blog/history-of-threat-modeling) but can be applied to your personal privacy to help stay on track and focus on what really matters to you.
* What personal information are you protecting?
	* Example: Sensitive messages, photos, your sexual orientation, race, religious or political views, etc.
* Who are you protecting that information from?
	* Example: family members, strangers on the internet, companies and advertisers, a government, etc.
* How much time and money are you willing to invest into protecting this information?

Answering these questions will help you better understand your goals with protecting your privacy and ultimately save you time and headaches in the future.

## Secure, encrypt, & backup devices
Anything can happen while traveling, and that includes losing your phone or other devices. You need to be prepared for this *before* it happens to avoid turning an inconvenience into an absolute nightmare because you don't have a backup of your data, your phone didn't have a passcode, or a thief can see all of your unencrypted files on your laptop.

1. Set strong, unique passcodes and passwords on *all* of your devices; opt for alphanumeric passwords wherever possible; store everything in a [password manager](https://www.pcmag.com/explainers/why-you-need-a-password-manager-and-how-to-choose-the-right-one)
2. Set up multi-factor authentication methods, preferrably [TOTP](https://en.wikipedia.org/wiki/Time-based_One-Time_Password), for any accounts that offer them (especially your email and password manager)
3. Create backups for anything you can't or wouldn't want to lose: photos, files, and especially *2FA recovery codes*
	* Follow the [3-2-1 rule](https://www.veeam.com/blog/321-backup-rule.html): three separate copies of your data, two types of storage, and at least one copy off-site
	* Consider using a [encrypted cloud storage provider](https://www.cloudwards.net/best-encrypted-cloud-storage/) for online backups that supports [zero-knowledge encryption](https://www.keepersecurity.com/resources/zero-knowledge-for-ultimate-password-security.html)
4. Make sure that your devices have [full disk encryption](https://en.wikipedia.org/wiki/Full_disk_encryption). 
   Popular OS-level solutions include:
	* [Bitlocker](https://support.microsoft.com/en-us/windows/device-encryption-in-windows-cf7e2b6f-3e70-4882-9532-18633605b7df) for Windows
	* [FileVault](https://support.apple.com/guide/mac-help/protect-data-on-your-mac-with-filevault-mh11785/mac) for MacOS
	* [Linux Unified Key Setup (LUKS)](https://www.cyberciti.biz/security/howto-linux-hard-disk-encryption-with-luks-cryptsetup-command/) for Linux
	
    Here are some third-party FOSS solutions (for encrypting files/volumes):
	* [Cryptomator](https://cryptomator.org/)
	* [VeraCrypt](https://veracrypt.fr/)

For brownie points, you can even encrypt your backups before uploading them to an encrypted cloud storage provider to mitigate any risk of your data being exfiltrated if that provider and their encryption keys were to be compromised.
[Yo dawg...](https://knowyourmeme.com/memes/xzibit-yo-dawg) I heard you like encrypted backups.

## Freeze your credit
This section is for my US readers, but you should take whatever equivalent steps you can in your country. 

Although not one of the first things you might think of when preparing to travel, [freezing your credit](https://www.experian.com/blogs/ask-experian/what-is-a-credit-freeze/) is an important measure to protect yourself from identity theft and fraud while you're away.
One of the last things you want to hear during your trip is that someone stole your identity while you were relaxing on the beach none the wiser.
Submitting a credit freeze to each of the [three credit bureaus](https://www.investopedia.com/personal-finance/top-three-credit-bureaus/) is an added layer of security and peace of mind that scratches one more item off the list of things that can go wrong.
The process is takes less than 5 minutes in total. If you haven't already, create an account with [Equifax](https://my.equifax.com/membercenter/#/login), [Experian](https://usa.experian.com/), and [TransUnion](https://service.transunion.com/). 
Then all you have to do is submit a freeze. It's just a good idea to have these accounts created anyways, especially if you want to request your free credit report from any of them.

{{< figure align=left src="/images/transunion-freeze.png" >}}

Freezing your credit is now completely free [thanks to the FTC](https://consumer.ftc.gov/consumer-alerts/2018/09/free-credit-freezes-are-here), and you can submit a freeze as often as you need. 
There's really no excuse *not* to do this for most people, regardless of if they're traveling or not, especially given that you can even [schedule a thaw](https://www.experian.com/blogs/ask-experian/how-to-unfreeze-your-credit-report/) 
on your credit for it to un-freeze by the time you return.

My advice: always keep your credit frozen until you know you'll need to unfreeze it, which only takes a few minutes. Even when you're not traveling.


## SIM cards
A [SIM card](https://en.wikipedia.org/wiki/SIM_card) (Subscriber Identity Module, for the curious) is your ticket to connecting to a cell network and sending and receiving phone calls and texts. Traveling without one would be a logistical nightmare.

Depending on the country you travel to, your existing cell plan will probably still work and will likely just charge you daily roaming fees (unless you have an international plan). Calls and texts may also incur additional fees while you're abroad. However, this may be significantly more expensive than buying your own SIM card after arriving. 

Before continuing, you need to check if there are any SIM card registration laws, otherwise known as Know Your Customer (KYC) requirements, for the country you are visiting. This may change change your game plan. 
Here's a [lookup tool](https://www.phonetravelwiz.com/phone-travel-options/sim-card-registration/) for which countries have SIM card registration laws.

Keep in mind that some services or apps in the country you visit may not accept foreign phone numbers, which, coupled with the potential savings, means that there's no reason for you to be giving out your primary phone number in a foreign country. An anecdote I have for this was trying to register for [DiDi](https://web.didiglobal.com/mx/pasajero/) in Mexico (an Uber alternative), which only accepted a Mexican phone number.

In some countries, it is trivially easy and inexpensive to purchase a new SIM card. Throughout my time in Mexico, I saw people selling SIM cards in the street, in the subway, and in flea markets; a new "chip" was usually no more than $2.50 USD. 

When purchasing the SIM card, pay in cash to avoid directly linking your identity to your phone with a credit card. The same goes for purchasing more data or a cell plan.

Now that you have a cell plan and phone number, I also recommend looking into a (paid) service to generate burner phone numbers to help [compartmentalize your identity](https://medium.com/codex/everyone-should-implement-digital-compartmentalization-e1cc45395db2) across different numbers linked to different businesses or accounts. Some services worth checking out include [Hushed](https://hushed.com/), [Burner](https://www.burnerapp.com/), [MySudo](https://anonyome.com/individuals/mysudo/), and (ironically?) [Google Voice](https://voice.google.com/).

But what if you rely on your phone number to text friends and family back home? I recommend letting people know when you will be leaving and how they can reach you, which should be through a secure instant messenger app, as I'll discuss in a moment.

### eSIMs
An [embedded SIM card](https://www.digitaltrends.com/mobile/esim-explainer/#dt-heading-when-can-i-start-using-an-esim) (eSIM) removes the physical card from your phone and allows you to purchase SIM cards digitally through a dedicated service. Similar to SIM cards, eSIMs may also be subject to ["eKYC"](https://www.airalo.com/blog/whats-an-ekyc-and-why-do-some-esims-require-it) requirements which you will need to check with first.

Although I don't have any experience with eSIMs yet, I understand them to be [more secure and convenient than private](https://www.reddit.com/r/privacy/comments/144amd7/is_an_esim_is_more_secure_than_a_physical_sim/):
* Phone numbers can be purchased instantly through an app or website; but these numbers are linked to your account/identity (unlike with cash payments)
* A stolen phone with an eSIM can be easily deactivated and a new phone number provisioned; there is no SIM card to plug into another phone

{{< figure align=left src="/images/sim-vs-esim.png" >}}
*via [mintmobile.com](https://www.mintmobile.com/blog/esim-vs-physical-sim-cards-what-you-need-to-know/)*

## Messaging & texting
Believe it or not, outside of the United States not everyone has an iPhone. In fact, here is a sobering [tweet by World of Statistics](https://x.com/stats_feed/status/1671378198477643777) that shows the percentage of annual salary, by country, required to buy a new iPhone 14 Pro, which explains the proliferation of different phone brands across across the world, as seen below.

{{< figure align=left src="/images/smartphone-market-share.png" >}}
*via [vividmaps.com](https://vividmaps.com/most-popular-mobile-brands/)*

### SMS
**SMS (Simple Messenger Service)** is also simply insecure. [This article](https://www.howtogeek.com/709373/why-sms-text-messages-arent-private-or-secure/) by How-To Geek explains why SMS is neither private nor secure, and why you should not use it:
* SMS messages are not encrypted
* Because of this, your cell carrier, criminals, and [the government](https://sls.eff.org/technologies/cell-site-simulators-imsi-catchers) can read any messages you send or receive
* [SIM swapping attacks](https://www.microsoft.com/en-us/microsoft-365-life-hacks/privacy-and-safety/what-is-sim-swapping) allow scammers to hijack your SIM card with a modicum of personal information about you to trick your cell carrier by social engineering, and can target anyone, including [celebrities and cryptocurrency holders](https://www.pcmag.com/news/10-suspects-arrested-for-sim-swapping-attacks-on-us-celebrities)

{{< figure align=left src="/images/sim-swap.png" >}}
*via [SNBonline.com](https://www.snbonline.com/about/news/how-to-prevent-sim-swap-fraud)*

### RCS
The new and improved **Rich Communication Services (RCS)** protocol, which provides [numerous enhancements over SMS](https://www.androidauthority.com/rcs-vs-sms-3330098/#3) is quickly gaining adoption as more cell phones and carriers are finally enabling compatibility. Beyond various quality-of-life and nice-to-haves being added such as media attachments, removed character limits, typing indicators, and group chats, and most notably, **encrypted messages**. In 2023, [Google enabled encryption for RCS conversations](https://www.theverge.com/2023/8/8/23824800/google-messages-rcs-end-to-end-encryption-default-group) using Google Messages by default. In late 2024, the Global System for Mobile Communications Association (GSMA), a non-profit that represents the world's largest mobile telecom businesses, announced that it was beginning development of [cross-platform RCS messaging](https://thehackernews.com/2024/09/gsma-plans-end-to-end-encryption-for.html) that would allow Android and iOS users to enjoy the same E2EE communications that they already enjoy, but together.

However, there are still a few barriers holding back RCS:
* Existing ubiquity of third-party messenger apps
* Apple [stubbornly blocked support](https://www.theverge.com/2022/9/8/23343336/apple-tim-cook-imessage-blue-green-bubbles-texting-rcs) for RCS until iOS 18, and the feature is [not enabled by default](https://www.tomsguide.com/phones/iphones/can-you-get-rcs-messaging-on-your-iphone-heres-how-to-find-out-and-enable-it-in-ios-18); adoption will continue to be rocky
* Cell phone manufacturers and cell carriers both must enable compatibility for RCS (including for iOS users)

{{< figure align=left src="/images/rcs-vs-sms.png" >}}
*via [bsg.world](https://bsg.world/blog/what-is-rcs-messaging/)*

### Third-party messengers
Now that we know that SMS, RCS, and iMessage are not realistic options for traveling abroad, where does that leave us? With instant messengers, of course. 

With so many users on different platforms, accompanied by the shortcomings of SMS and the slow rollout of RCS, instant messengers like Facebook Messenger and WhatsApp have taken hold across the world. They offer the same amenities and features like group chats, cross-platform compatibility, and (generally) end-to-end encrypted messaging that provide an appealing package for users across the world.

NordVPN released an excellent comparison of the [most secure messaging apps](https://nordvpn.com/es-mx/blog/most-secure-messaging-app/) which analyzes the differences in data collection and security between these apps that are used by billions daily. 

{{< figure align=left src="/images/secure-messenger-apps.jpg" >}}
*via [nordvpn.com](https://nordvpn.com/blog/most-secure-messaging-app/)*

Spoiler alert: [Signal](https://signal.org/) wins, by a mile. [Wickr](https://en.wikipedia.org/wiki/Wickr) was previously one of the only technical competitors to Signal, but AWS announced that it would [shut down the free service](https://www.pcmag.com/news/amazon-owned-secure-messaging-app-wickr-me-to-shut-down) only a year after acquiring it due to the sinister ethical and legal challenges of running an end-to-end encrypted messaging service.

But this is a blog post about travel, so you're going to want to use the messenger that everyone else is using. You should do some research based on where you're going beforehand, though it probably won't be surprising. WhatsApp completely dominates the user share for messengers globally. In fact, "[WhatsApp is used by over 90% of people](https://www.statista.com/statistics/1311229/whatsapp-usage-messaging-app-users-by-country/) in countries where it is the leading messaging app." So chances are that you're going to need to use WhatsApp wherever you go.

{{< figure align=left src="/images/most-popular-chat-apps.png" >}}
*via [nordvpn.com](https://nordvpn.com/blog/most-secure-messaging-app/)*

I am a Signal fanboy, but in my case in Mexico I had to bite the bullet and install WhatsApp. Almost everyone uses the app in Mexico, including local businesses which only accept reservations or appointments via messaging them through the app (and sometimes Facebook). It was one of the biggest culture shocks for me coming from the U.S. Trying to abstain from Meta here will only guarantee that you have a hard time making friends or any kind of reservation, and people will look at you like a lepyr if you ask to use anything that isn't Facebook, Instagram, or WhatsApp. I concluded that it was not a hill I was willing to die on and ruin my trip.

The compromise I made was to purchase a SIM card at a 7-Eleven (in cash) then use that phone number to create a new WhatsApp account, which I would only use in Mexico. It's not perfect--nothing is when you travel-- but I can at least relax knowing that all messages are E2EE and my activity is siloed to the country that I'm in.

## Public Wi-Fi
Times have changed, and the reality is that public Wi-Fi networks aren't inherently dangerous like they used to be thanks to security improvements in web browsers (with [HTTPS-only mode](https://support.mozilla.org/en-US/kb/https-only-prefs)), [personal firewalls](https://en.wikipedia.org/wiki/Personal_firewall), and [networking standards](https://en.wikipedia.org/wiki/Wi-Fi_Protected_Access). This means that your browser is no longer making plaintext HTTP requests to servers, your computer likely has a competent firewall and anti-virus, and the network you're connected to is encrypted. 

However, this doesn't mean that public Wi-Fi is without risk. Although malicious actors are limited by these security improvements, they still have a few tricks up their sleeves such as:
* [Man-in-the-Middle attacks](https://www.ibm.com/think/topics/man-in-the-middle), where an attacker connects to the same public network and places themselves in between two communicating parties, intercepting all traffic, which allows for eavesdropping and potentially manipulating messages
* [Malicious hotspots ("evil twin attacks")](https://us.norton.com/blog/emerging-threats/evil-twin-attack), a type of MitM attack where the attacker mimicks an existing network, often using a duplicate SSID network name ("Starbucks WiFi"), or just   advertises something like "FREE PUBLIC WIFI" to trick users into connecting to it.

{{< figure align=left src="/images/wifi-gratis.jpg" >}}
*via [maspormas.com](https://www.maspormas.com/urbano/wifi-gratis-en-la-cdmx/)*

To re-iterate, the danger isn't the Wi-Fi network itself, it's the fact that it's public and anyone can connect to it. Therefore, it is prudent to treat all public networks like they are dangerous, and take a few steps to add some peace of mind: 
* Enforce HTTPS-only mode on your browser to make sure all of your requests on the internet are encrypted
* Use a VPN to encrypt all of your traffic between you and the router
* Similarly, a [travel router](https://www.tomsguide.com/computing/vpns/heres-why-you-should-consider-using-a-vpn-router-for-travel) is useful if you're traveling with multiple devices (that might not be able to connect directly to a VPN) and adds an additional layer of protection between your devices and the network by forcing all your devices to communicate with the router before reaching the network gateway
	* Consider options that support open-source routing operating systems like [OpenWRT](https://openwrt.org/) and also installing [custom VPN profiles](https://www.bleepingcomputer.com/vpn/guides/how-to-install-a-vpn-on-your-router/)
* If your device supports it: enable [MAC-address randomization](https://www.guidingtech.com/what-is-mac-randomization-and-how-to-use-it-on-your-devices/) for each network you connect to, masking your device's unique hardware identifier (if your device supports random addresses *per connection*, even better!)

{{< figure align=left src="/images/travel-router.png" >}}
*via [vpnuniversity.com](https://www.vpnuniversity.com/routers/setup-two-routers-with-dedicated-vpn-router)*

## Bluetooth connections
During your travels, there's lots of foreign devices that you might connect to via Bluetooth, such as the radio in your rental car or the entertainment system in the airplane or bus ride, for example. You might think that such a cut-and-dry, single function technology would be harmless for your privacy, and that is where you would be *technically* right, but not really.
{{< figure align=left src="/images/yes-but-no.png" >}}

### Surveillance
However, as with a [long list of inventions](https://blog.empowergadgets.com/12-inventions-that-had-a-different-purpose-than-they-are-used-today/)that now have a different purpose from when they were originally created, BlueTooth has been perverted by retail corporations and national governments into a surveillance technology that easily and inexpensively tracks your every move. Retailers commonly use [BlueTooth beacons](https://www.nytimes.com/interactive/2019/06/14/opinion/bluetooth-wireless-tracking-privacy.html) which track your movements from the time you enter the store until you leave, which allows them to identify shopping habits and patterns, trigger relevant offers through their mobile apps, and deliver personalized ads. This [Shopify article](https://www.shopify.com/retail/the-ultimate-guide-to-using-beacon-technology-for-retail-stores) gives a brief overview of how Bluetooth is used by marketers and it's pretty unnerving.

Similarly, governments have begun to implement a more sinister form of BlueTooth surveillance, such as that along the U.S.-Mexico border, as [this EFF article describes](https://www.eff.org/deeplinks/2024/05/add-bluetooth-long-list-border-surveillance-technologies), where certain counties have purchased a Bluetooth scanner which can "track devices that emit Bluetooth signals, including cell phones, smartwatches, wireless earbuds, and car entertainment systems". This works by exploiting Bluetooth devices' desire to broadcast their [device address](https://novelbits.io/bluetooth-address-privacy-ble/) to the world, where that address can be used to link other to other devices and even individuals.

So what do you have to do? It's simple. Full stop: **turn off** your Bluetooth *before* you enter an airport or border crossing. I argue that you should just entirely power off all of your devices as well, whenever possible, though I know this isn't always realistic because you might need your phone for a ticket or ID - try to use printed copies to avoid this.

Side note: one frustrating thing about iOS is that turning off your Bluetooth in the Control Center does not permanently disable it, so the phone will begin to scan for devices again after a period of time. Do some research for your device to learn how to disable it permanently. But again, I recommend powering off the device entirely.

{{< figure align=left src="/images/bluetooth-beacons.png" >}}
*via [mouse.kr](https://www.mouser.kr/applications/bluetooth-5-mesh-networking-standard/)*

### Allowing access to contacts & calls
Earlier I mentioned rental cars. Newer rental cars will commonly have a head unit that you can connect your phone to in order to use Bluetooth, or Car Play/Android Auto. In the rentals that I've been in, I've noticed that people will connect their phones to the head unit, often allowing access to their contacts and phone calls, and then forget to unlink the device before they return the car. What this means is that anyone else who uses the car after them can look through their contacts and call history. It's easy to understand how someone could forget such a seemingly small detail, but this could lead to a serious violation of that person's privacy. You wouldn't want a stranger to be able to go through your text messages, contacts list, or see who you've been talking to on the phone, right? Well that's unfortunately what can happen by allowing this access and not unlinking the device. 

I am *not* blaming the individuals here, rather I believe it is the onus of the rental company to ensure that this data gets deleted each time the car is returned so that other customers can't snoop through such information.

{{< figure align=left src="/images/android-bluetooth-screen.png" >}}
So what should you do?
* Do not allow access to contacts/call history unless you know that you need to do so
	* You can still make phone calls, play music, and use navigation without granting this permission
* When you are done, go to the settings of the head unit or console that you are connected to and deliberately "Forget" your phone or device that you connected. Do this *before* forgetting the device on your phone
* If you see other peoples' devices that they forgot to disconnect, do the right thing and Forget those devices as well

## "Burner" phones
Depending on your threat model and concerns about safety in the place that you are visiting, "burner" phones may be an option to consider. I emphasize, with quotations around "burner", that I am *not* talking about those dummy flip phones that bad guys use in the movies and then destroy after taking a phone call. Buying something like this is likely counterproductive for your needs as a traveler and overkill for your threat model; I'm sure you probably get added to some kind of list for buying one now too.

What I am actually talking about is a cheap backup phone that only has the essential apps or information you need loaded onto it, which you can use as a daily driver if you are worried that your phone might get lost or stolen during your travels. Carrying around an expensive phone in some countries is an easy way to draw unwanted attention, and a cheap phone can help you not stick out so much (because sometimes you can never really "blend in").

By buying a cheap (ideally second-hand) phone and setting up only the bare minimum to get around, you can worry less about the implications of data loss or exfiltration, and more importantly, you can spend more time enjoying your trip. I actually advocate for a burner phone more from the angle of [digital minimalism](https://calnewport.com/on-digital-minimalism/) than I do for privacy or security, although there are benefits to be had in all regards. 

A caveat worth mentioning: many cheap smart phones that you may come across are [data harvesting machines](https://www.androidauthority.com/xiaomi-privacy-cheap-phone-1118444/). Just like the old saying goes, there's no such thing as a cheap? lunch, and lots of the more economical options are discounted at the [cost of your privacy.](https://arxiv.org/abs/2302.01890) There's also something to be said about truly "owning" your devices. I purchased a Xiaomi phone in Mexico just to play around with it and I was pretty shocked by how little control I had over  it. Every time I turned it on there was new bloatware being installed. I tried to install [LineageOS](https://lineageos.org/) to make it a little more usable, only to learn that Xiaomi [locks the bootloader](https://miuirom.org/updates/xiaomi-bootloader) behind a "Mi" account that link you need to link to the device; so you need to create an account first, which requires a phone number and email address. 

I factory reset the phone and threw it into a sock drawer, and I'm going to exchange it for an unlocked phone compatible with LineageOS the next time I go back.

Any unlocked phone that is supported by a privacy-friendly custom ROM such as [LineageOS](https://wiki.lineageos.org/devices/), [DivestOS](https://divestos.org/pages/devices) (a privacy-focused fork of Lineage), and [GrapheneOS](https://grapheneos.org/faq#device-support) would be sufficient. However, Graphene is exclusive to Pixel devices which are pricier and harder to come by depending on the country.

## Payments
### Cash
How you pay for stuff is going to depend on where you're visiting, but the general rule is that **cash is king**. In Mexico, it was also completely required: paying for food and even public transit was often cash-only. There were also multiple occasions where I went to a restaurant that "accepted" card, but the reader had no internet connection or the business charged a fee for using card. Coming from the U.S., this was another culture shock and challenge for me as I was not used to carrying much cash on me, and much less *coins*, but I quickly grew to enjoy dealing with cash. This is also a reminder that [credit cards psychologically manipulate us](https://mitsloan.mit.edu/experts/how-credit-cards-activate-reward-center-our-brains-and-drive-spending) into spending more.

### Card
Realistically, however, the time will come when you do need to pay with card, whether you don't have enough cash on hand, or you want to take advantage of cashback or rewards points for a large purchase. There are a few things you can do to enjoy the benefits of credit while preserving a modicum of privacy abroad.
#### Contactless payments & digital wallets
"Tap to pay": you've heard and seen it before, and you already know that it works on phones now through services like Apple, Google, and Samsung Pay (among others), known as "[digital wallets](https://www.nerdwallet.com/article/credit-cards/what-is-a-digital-wallet-and-how-does-it-work)". 

{{< figure align=left src="/images/tap-to-pay.png" >}}
*via [visa.com](https://usa.visa.com/pay-with-visa/contactless-payments/contactless-payments.html)*

What you might not have known is that behind the scenes, these digital wallets actually mask your credit card details by generating a "token" (through a process called [tokenization](https://stripe.com/resources/more/payment-tokenization-101)) which essentially hides your credit card from the vendor. This marginally protects your information from the business, but you are still ultimately sharing your transaction information with the service provider (such as Apple), and of course, your bank. However, this is a happy medium when you need to use card, especially for the improved security and peace of mind not having to worry about [card skimmers](https://www.capitalone.com/learn-grow/privacy-security/credit-card-skimmers/), and the authentication required before making payments.

Physical cards are less ideal. Only swipe or insert your card if there is no contactless option available, and in such a case, be cognizant of skimmers.


#### Virtual cards
Where contactless payment services like Apply Pay hide your payment information by generating temporary tokens for each transaction, [virtual cards](https://www.cnet.com/personal-finance/credit-cards/advice/what-is-a-virtual-card-and-how-do-you-use-it/) remove that payment information from the equation by generating disposable 16-digit cards funded by your bank account. Virtual cards also offer budgetary benefits like being able to set spend limits for specific cards, lock cards to specific vendors, and block recurring payments from expensive subscriptions. The largest consumer virtual card provider (which is only available in the U.S.) is [Privacy.com](https://privacy.com/).

{{< figure align=left src="/images/virtual-card.png" >}}
*via [Privacy.com](https://privacy.com/blog/is-privacy-com-safe-an-overview-of-privacys-security-practices)*

Privacy.com recently announced the beta release of their [digital wallet integration](https://privacy.com/blog/how-digital-wallets-bring-security-to-payments) for Premium members, which allows for adding virtual cards to digital wallet providers like Apple Pay, Google Pay, and Samsung Pay. This gives you the best of both worlds and is absolutely the best approach for paying with card in-person. Just make a virtual card, throw it into your digital wallet, and you're good to go.

{{< figure align=left src="/images/digital-wallet.png" >}}
*via [Privacy.com](https://privacy.com/blog/how-digital-wallets-bring-security-to-payments)*

To re-iterate:
* [Cash rules](https://youtu.be/or5C2jV1qRc)
* Where cash is not an option, use a virtual card within a digital wallet 
* Where cash is not an option and no contactless pay is available, check for card skimmers
* For online purchases, use a virtual card

## Email aliases
We're already asked for our email address pretty often at home, now just imagine while traveling. Here are some common occasions where you'll be solicited for your email address (and probably your phone number too):
* Signing up for a hotel or accomodation
* Booking reservations for tours, activities, or other outings
* Creating new accounts for things like local transit or loyalty programs
* Filling out government travel forms

Clearly, you're going to have to give out your email address pretty frequently- even for activities or services that you're never going to do or need again. And you can rest assured that most businesses are going to add you to their mailing list. Or worse: they'll get hacked, and your email address will fall into the hands of whoever stole it (and whoever subsequently buys it).

That's what happened to me. In 2023, I visited Montreal and I wanted to rent a bike to explore the city, but the only option was those self-service rent-a-bikes on the side of the street; in Montreal they have "[BIXI](https://bixi.com/en/)". I later found out that they are or were owned by Lyft. I remember being in disbelief that I had to sign up for an account with my email and phone number just to rent a crappy bike for 30 minutes, but I was on vacation and in the mood to explore so I acquiesced. When all was said and done my account had been created; I also lost cell service so I wasn't even able to actually rent the bike, but that's not the point. 

When I created this account, I used a [random email alias](https://simplelogin.io/blog/what-is-an-email-alias/) that would forward to my primary inbox. This allows me to hide my actual email address and generate a unique email specific to each service or vendor that I share my email with.

Fast forward about 12 months and I receive two phishing emails. I checked to see which address they were sent to in order to see how and where they got my email and, lo and behold, I see that these phishing emails were sent to the email alias that I had created a year earlier when I signed up for BIXI in the streets of Montreal. I never received or was able to find any news from BIXI about a security incident, but my money is on them being hacked and not giving notice to consumers.

{{< figure align=left src="/images/email-alias.png" >}}
*via [davescomputertips.com](https://davescomputertips.com/how-to-use-email-aliases-with-bitwarden/)*

So yeah, use an email alias. It lets you cut down on the amount of email you receive, while shielding your primary email address and identity and protecting you from data breaches. If anything ever happens, or if you just don't need the alias anymore, you can easily pause or delete the address. Aliasing is easily one of the best tools that exist today to protect your privacy.

There are a few popular services out there (including built-in aliases for Outlook and Gmail), but I recommend FOSS solutions like [addy.io](https://addy.io/) and [SimpleLogin](https://simplelogin.io/), which also integrate with several password managers to make it easy to create new accounts with random aliases.

Pro tip: email aliases are also not just for receiving email. You can to send outgoing mail addressed from your alias so you don't expose your original address.

## Handling identity documents and passports
To start, as a general rule, you should have a paper and digital copy of:
* Your primary identification (such as a driver's license)
* Your passport
* Any other relevant documents that you know you will need, such as reservations or appointments

Having these handy is important if you get asked by customs what you will be doing or where you will be going, and having separate copies is essential if you lose one or the other.

That's all and well, but after all the research and planning I did before my trip, I was shocked when, 
during my time in Mexico, multiple hotels and hostels took a photocopy of my ID- something I had never seen before in the United States. I found a [reddit thread](https://www.reddit.com/r/privacy/comments/xzdm6u/how_do_you_guys_handle_hotels_photocopyingtaking/) discussing exactly this, and it seems to be common practice in some countries in Latin America and Asia. 

I had no expectation of privacy coming into my travels, but that doesn't mean I shouldn't feel uncomfortable about a copy of my driver's license sitting on the computer or the printer in the front desk of some tiny hostel, or in the WhatsApp messages of a building attendant.

So what can be done about this?
1. Ask to have the photo deleted upon leaving. Be nice, which goes a long way and is just good life advice.
2. If possible, provide a form of identification that provides only the *minimum necessary information* about you, reducing the amount of personal information you share. This is a principle referred to as "[data minimization](https://en.wikipedia.org/wiki/Data_minimization)"  in the data privacy and protection field. 
   
   For example, a U.S. drivers license discloses sensitive personal information including address, height, weight, even organ donor status. However, a U.S. passport has none of those items. On paper, a passport sounds pretty sensitive, but if you think about it a driver's license is much more sensitive and identifying. Driver's licenses numbers are even used as a form of authentication sometimes. But the only time your passport number is ever used is traveling between countries, and any government is going to know it. I'd argue there's a lot less harm in having your passport number revealed than your DL#. 
   
   For this reason, I recommend U.S. citizens elect to use their passport as a form of identification whenever possible, and even consider getting a [passport card](https://en.wikipedia.org/wiki/United_States_Passport_Card) for $30.
3. If solicited for any other information, for example, at a hotel: provide a burner phone number and a PO box. 

## Navigating border crossings and airports
Some previous points apply here:
* DO NOT lie or provide false information to a government
* Use an email alias (or dedicated travel email address) and backup phone number when filling out forms
* Encrypt your devices
* Power off your devices and Bluetooth before points of entry
* Accept that you can't be private all the time

Some suggested reading includes [this Proton article](https://proton.me/blog/border-crossing-protect-electronics) which discusses some of these points and others in more detail.

### Know your rights (or lack thereof)
Depending on the country you are visiting and your relation to that country (such as a resident, versus a citizen) you may have certain rights available to you during this process. It is your responsibility to do your research beforehand to understand what you can and cannot do here. Just because things are a certain way in your country doesn't mean they are (or should be) in another. Never try to "debate" a government official about your rights- either calmly exercise them or comply.

Also know what to expect. Sometimes border agencies will "request" your device for "inspection", which can mean browsing through your text messages to make sure that you're not working in the country without permission, or it can mean taking your phone to the backroom and scanning it through a forensics device like a [Cellebrite](https://en.wikipedia.org/wiki/Cellebrite_UFED) - nobody knows. It is on you to know whether or not you need to comply with such a request.

If you are seriously concerned about your devices being seized or inspected, you can (in ascending order of caution):
* Turn off biometric logins (fingerprint or FaceID, for example) - the Fifth Amendment does NOT prohibit the police from [compelling device unlocks using biometrics](https://arstechnica.com/tech-policy/2024/04/cops-can-force-suspect-to-unlock-phone-with-thumbprint-us-court-rules/); this can also be avoided by powering off the device to force [Before First Unlock (BFU) state](https://blogs.dsu.edu/digforce/2023/08/23/bfu-and-afu-lock-states/)
* Only travel with the bare minimum amount of data you need for your trip
* Mail the device to wherever you will be staying and collect it after arriving
* Completely wipe the device before crossing and then restore from a cloud backup afterwards
* An interesting discussion, but I do not recommend [hidden encrypted volumes](https://security.stackexchange.com/questions/135846/is-plausible-deniability-actually-feasible-for-encrypted-volumes-disks)

Here are some interesting articles about device searches and seizures at borders around the world:
* A [new 2024 ruling](https://techcrunch.com/2024/07/29/us-border-agents-must-get-warrant-before-cell-phone-searches-federal-court-rules/) finds that "U.S. border agents must obtain a warrant before searching the electronic devices of Americans and international travelers crossing the U.S. border"
* The Australian Border Force can ask to search your phone, and you can refuse at the [risk of being detained](https://www.abc.net.au/news/2022-01-24/can-border-force-search-your-phone-when-you-travel-to-australia/100774644)

### Say no to biometrics, if possible
Biometrics have been around borders and airports for decades now, but these technologies are becoming increasingly sophisticated and ubiquitous, especially in the U.S. as the TSA and CBP [push for further adoption](https://www.tsa.gov/sites/default/files/tsa_biometrics_roadmap.pdf) and test biometrics [in new environments](https://westsidenewsny.com/news/2024-11-24/cbp-announces-facial-biometric-test-for-inbound-vehicle-travelers-at-peace-bridge/).

{{< figure align=left src="/images/biometric-checkpoint.png" >}}
*via [identityreview.com](https://identityreview.com/u-s-airlines-are-expanding-biometric-services-for-passengers/)*

As a U.S. citizen, you have the right to decline biometric checks at airports, as [explained by this Vox article](https://www.vox.com/future-perfect/360952/summer-travel-airport-facial-recognition-scan). In my personal experience it takes almost the same amount of time to pass through without as it does with biometrics. However, this heavily depends on the agent that attends to you and how many questions they want to ask. 

Usually you will also see signage before going up to the agent that explains your rights and whether or not you may refuse a biometric scan, as shown in the picture above.

*Why bother refusing a biometric scan?* What's the point of having rights if nobody is willing to exercise them?

## Conclusion
Travel is incredibly rewarding, and a privilege. Enjoy it as much as you can. All of this information serves me to be able to enjoy my time abroad more thoroughly and uninterrupted, with a greater peace of mind free from distractions and doubt.