---
title: "Automotive privacy and DIY defense"
date: "2024-11-22"
description: "How smart cars collect and share your sensitive data, and what you can do about it."
tags:
  - FOSS
  - privacy
ShowToc: true
---


## Introduction
As cars become increasingly "smarter" and connected with our online world, they come equipped with features akin to those of smartphones. These advanced capabilities are made possible through a combination of sensors, cameras, and connectivity technologies that enable vehicles to collect and analyze data in real-time. Like smartphones, cars have evolved into mobile computers, but on a much larger scale with [higher levels of precision](https://www.azosensors.com/article.aspx?ArticleID=1905), collecting new types of data that can be used to identify and profile drivers. Therefore, it is crucial for automakers to safeguard this data. Yet, time and time again, they show us that they shirk this responsibility. 

Take Toyota, for example, who recently announced another data breach - this being their [third only within the last two years](https://www.bleepingcomputer.com/news/security/toyota-confirms-third-party-data-breach-impacting-customers/). In November 2024, [Ford suffered a data breach](https://www.cpomagazine.com/cyber-security/american-auto-giant-ford-alleged-data-breach-impacted-44000-customers/) that resulted in 44,000 customer records being published on the dark web.

{{< figure align=left src="/images/Toyota-August-data-leak.webp" >}}

Moreover when automotive companies aren't being careless with your data, they're being *reckless* with it. In 2024, General Motors [received ten federal lawsuits](https://www.pressreader.com/usa/las-vegas-review-journal/20240425/282445649119086) after it was revealed that they had "tricked millions of drivers" into signing up for their [Smart Driver program](https://www.forbes.com/sites/antoniopequenoiv/2024/04/24/general-motors-axes-onstar-smart-driver-system-after-privacy-and-insurance-complaints/), subsequently sharing this information with data broker [LexisNexis](https://www.pressreader.com/usa/las-vegas-review-journal/20240425/282445649119086).

In short, cars pose serious privacy risks. Don't take it from me, take it from the [Mozilla Foundation](https://foundation.mozilla.org/), who conducted a privacy review of 25 major automakers, and released their findings: ["Cars Are the Worst Product Category We Have Ever Reviewed for Privacy"](https://foundation.mozilla.org/en/privacynotincluded/articles/its-official-cars-are-the-worst-product-category-we-have-ever-reviewed-for-privacy/). 

Almost all major auto brands are sharing or selling customer data to third parties for marketing or the ever nebulous "business" purposes. And there's nothing stopping these manufacturers from changing those purposes at any time. As if things weren't already absurd enough, like cars [locking features behind a subscription model](https://medium.com/tech-topics/car-feature-subscriptions-are-here-to-stay-94feb8cce8fd), I encourage you to imagine a dystopian world where your own car serves you personalized advertisements, a [technology that Ford has recently patented](https://www.motortrend.com/news/ford-in-vehicle-advertising-patent/).

Whether you have a car that already comes equipped with a modern head unit with all the shiny bells and whistles, or you drive a 2003 Camry that never seems like it's going to give out, you have the option to try to manage and limit the collection taking place in your car currently, or nip the issue in the bud and replace the device collecting your data altogether.

## Is your car "spying" on you?
The data your car collects is used for much more than just letting you turn you car on with your phone or locate the vehicle if it gets stolen. Auto companies are actively sharing this data with [the insurance industry](https://reason.com/2024/03/25/stop-your-car-from-spying-on-you/) to hike insurance premiums for drivers based on factors like how fast you drive, where you go, and how far you drive - all of which is recorded by your car and can be shared directly with insurance companies for monetary gain.

These "smart" cars can also allow police to [bypass Fourth Amendment protections](https://www.governing.com/security/police-dont-need-a-warrant-to-pull-personal-data-from-cars) that would apply to you and your devices normally by instead going directly to your auto manufacturer and requesting that data *without the need for a warrant*.

This [EFF article](https://www.eff.org/deeplinks/2024/03/how-figure-out-what-your-car-knows-about-you-and-opt-out-sharing-when-you-can) walks through the types of data collected by cars and how to find out what data your car has collected and how to stop it from being shared.

A neat website you can check out is [Vehicle Privacy Report](https://vehicleprivacyreport.com/#), which allows you to view what types of data your car collects, who it sells/shares that data to, and other documents like the privacy policies and terms of service for your car.

{{< figure align=left src="/images/vehicle-privacy-report.png" >}}
*via [vehicleprivacyreport.com](https://vehicleprivacyreport.com/#)*



## Aftermarket Android head units
An automotive "head unit", also known as the stereo or "infotainment" system, is the interface for all multimedia and general system controls in your car. This is where the radio is in "analog" vehicles, and where the display screen is in newer digitally-equipped vehicles. Most automakers provide a proprietary head unit in their cars that come equipped with their own safety features and custom software, but this comes with all the aforementioned concerns about data collection and being locked into your manufacturer's hardware ecosystem when superior alternatives exist, as [this reddit comment](https://www.reddit.com/r/CarAV/comments/z60i6u/comment/iy0gyre/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button) discusses. And those alternative (aftermarket) systems can easily be purchased for a reasonable price and self-installed. 

{{< figure align=left src="/images/headunit-loading.jpg" >}}
*The bootup screen for my Android head unit.*

Most vehicles made in the last 20 years will have a compatible head unit that can be installed. Though some aftermarket systems also include their own proprietary operating system, many are based on Android. Android is the [most popular operating system in the world](https://www.businessofapps.com/data/android-statistics/) which runs on practically anything, and now even on cars that are over 20 years old. With a free, open-source operating system running inside your vehicle comes the liberty to do pretty much whatever you want, whether that be something as simple as playing music and podcasts from your phone over Bluetooth, or answering the age-old question: ["can it run DOOM?"](https://youtu.be/5mmiPT2avrY) (yes, cars can run DOOM).

{{< figure align=left src="/images/android-launcher.png" >}}
*The launcher I use.*

Most popular (and economical) Android head units are produced in China, which probably isn't a surprise to anybody. They generally include most of the basic features of any proprietary stereo system, including front and reverse camera software, Apple Car Play and Android Auto compatibility, Bluetooth, and lots of customization. Proprietary safety features that you'll find in most modern cars like lane assist, automatic cruise control, and other advanced options are obviously not included. However, the nature of an open-source operating system in your car unlocks so many more possibilities that would otherwise be completely unavailable, additionally offering tangible functional benefits beyond the peace of mind knowing that your data isn't being harvested by your vehicle manufacturer. 

I have had an Android head unit in my pre-digital vehicle for over 2 years now. When I first received the unit, I was overwhelmed by a 10-pound box full of messy cables, plugs, and antennae/receivers. But that shock turned to excitement as I realized I could equip my car with exactly what I wanted, no more, and no less. After half an hour of tinkering with the console and praying not to break anything (I did end up breaking a few plastic clips that were weakened by sun damage), I had a fully functional head unit in a car that previously could barely use the radio. The self-install process is super simple, albeit intimidating if you've never pulled out your car stereo before, but it's really difficult to royally mess anything up here. Now, I have a car with a:
* 9-inch IPS touchscreen panel
* Reverse camera
* GPS antenna for offline map navigation (to be paired with downloadble maps)
* 4G modem, for mobile hotspots
* Built in music library, Bluetooth, CarPlay/Android Auto, et. al
* All the perks of the Android OS

{{< figure align=left src="/images/headunit-install.jpeg" >}}
*A look behind the scenes.*

What excites me is that my car was manufactured before most of these things even existed. And that is just the list of hardware. Remember that I said that this was Android? Yeah, that Android... with the Google Play Store. This means that this system is capable of running any Play Store app you can think of. Netflix, YouTube, Spotify, mobile games, whatever your sick heart desires. Of course, I am not going to download *any* of those things in my car (and neither should you) for the safety of myself and others around me, but also because this is a blog focused on privacy. 

However, because this is Android, we are able to control granular permissions on an app-by-app basis, so if there is an application that you really need, you are able to connect to the Play Store, download the app, and then disable the Play Store and/or switch off network permissions wherever necessary. Out of habit, I've disabled any non-essential apps and granted only the bare minimum permissions needed everywhere else -- this serves as a safeguard in case the device does connect to a network for whatever reason.

{{< figure align=left src="/images/android-permissions.png" >}}
*Denying app permissions for Google Chrome, which I have no intention of using- in my car, or otherwise.*

Because my head unit comes with a built-in file manager, I elect to install the .APKs for my apps via USB as to avoid giving the unit any network permissions at all. This way I don't need to trust the manufacturer because the device is completely offline. This also gives me the added benefits of being able to verify the source of the APK and install apps that aren't found on the Play Store or F-Droid all with the convenience of a physical keyboard (seriously, those touch screen keyboards are painful). I also ripped out the old aux cord module in the car and replaced it with a female USB slot that connects to the back of the head unit for a more plug-and-play experience.

{{< figure align=left src="/images/android-file-explorer.png" >}}
*The built-in file explorer where I can transfer files to and from a USB.*

One such app that I've installed is an on-board diagnostics (OBD2) reader for diagnosing any issues with my car. [OBD2](https://www.csselectronics.com/pages/obd2-explained-simple-intro) is a "standardized protocol that allows extraction of diagnostic trouble codes (DTCs) and real-time data" via a reader device that hooks into the car's OBD port (you may have heard your mechanic refer to this generically as the "computer" in your car). These devices can range from ten to hundreds of dollars based on their capabilities and accuracy; I decided to pick up a very cheap [ELM 327 microcontroller](https://en.wikipedia.org/wiki/ELM327) just to test things out for fun. 

On the head unit, I installed a FOSS app called [AndrOBD](https://github.com/fr3ts0n/AndrOBD) which connects to the ELM327 adaptor via Bluetooth to relay any vehicle and diagnostic data that it can find. The app was able to confirm general info about my car and didn't find any issues, but it otherwise didn't fetch much useful data-- I'm not sure whether this is a fault of the app or the limitations of the ELM 327 paired with the age of my vehicle. As a quick aside, launching the app from the head unit in my car worked fine and required no permissions other than BlueTooth. However, I could not get the app to work properly on my phone as the app is still [limited to Android 13](https://github.com/fr3ts0n/AndrOBD/issues/282) and it also [requires superfluous permissions](https://github.com/fr3ts0n/AndrOBD/issues/270), though this could be addressed with an application firewall and [scoped storage](https://source.android.com/docs/core/storage/scoped?hl=es-419).

There are almost limitless options you can tinker with like any Android device, such as [custom launchers](https://xdaforums.com/t/app-launcher-vivid-best-launcher-for-driving.4308751/) for your car, but at the end of the day, this is a car. The only time I'm using it is to drive somewhere, and I'm not spending time hanging out in my car to watch a movie or look at cool launch animations. Navigation and a media player are realistically the only important apps that most drivers will need, and these are already packaged into Car Play/Android Auto in one sleek solution, or a plethora of offline alternatives. 

## Offline Android Auto
Besides a reverse camera, the biggest incentive for buying one of these head units is the Car Play and Android Auto capabilities. They immediately turn any old car into a modern interface that can be used for convenient navigation and media playing (music, podcasts, audiobooks, etc.), arguably while reducing distractions on the road and improving your safety.

Although my head unit supports wireless Car Play/Android Auto, I elect to use a wired connection for Android Auto because it also conveniently charges my phone at the same time and I've noticed the connection is more reliable. However, this also has the added benefit of granting fewer permissions to the app. In my setup, the app is offline and can only connect to BlueTooth, access the Phone for calls, and receive Notifications from those apps whitelisted for Android Auto. Some apps may not show up in your launcher because they come from an [untrusted source](https://www.groovypost.com/howto/android-allow-install-apps-unknown-sources/), meaning anything not installed via the Play Store. To fix this, simply [enable developer options](https://9to5google.com/2023/01/25/how-to-enable-developer-mode-in-android-auto-and-why-you-might-want-to/), go to "Developer settings" in the drop-down menu, then select "Unknown sources" at the bottom. From there, go back to Android Auto and click on "Customize launcher" to select whatever apps you want to be visible from your head unit.

I recommend using a navigation app that supports downloadable offline maps. I encourage you to consider FOSS solutions based on OpenStreetMap like [Organic Maps](https://organicmaps.app/) and [OsmAnd](https://www.osmand.net/). But I get it, and sometimes these solutions just don't cut it, in which case Google Maps with offline maps and no network permissions is a very effective solution and a happy-medium.

### Android Auto on GrapheneOS
For context, I am using [GrapheneOS](https://grapheneos.org/), which recently [added support for Android Auto](https://grapheneos.org/usage#android-auto) in early 2024. This allows for Android Auto to be installed through Graphene's revolutionary [sandboxed Google Play](https://grapheneos.org/usage#sandboxed-google-play), which allows for Google Play (and subsequently Google Play Services) to be installed like any ordinary app without granting it "highly priviliged access" that it would normally require otherwise (and without needing to sign into a Google account). 

{{< figure align=left src="/images/android-auto-preview.jpeg" >}}

As with the majority of my experiences using Graphene, Android Auto mostly works. I use "mostly" deliberately here, as the core experience and features that you would expect are functional and require minimal troubleshooting. However, small nice-to-have's like voice controls and text-to-speech to play messages do not work. Also, navigation apps need to be installed via the Play Store (ahem, [Aurora Store](https://aurorastore.org/)) in order to be recognized. FOSS navigation alternatives like [Organic Maps](https://organicmaps.app/) or [OsmAnd](https://osmand.net/) supposedly work, but I have not tested them just yet.

{{< figure align=left src="/images/android-auto-media.jpeg" >}}

## Conclusion
If you already have a newer vehicle equipped with a system collecting (and possibly sharing) data - get informed. Learn about what kinds of data your car is collecting and what you can do about it by visiting the privacy center for your manufacturer. There is usually a page hidden somewhere in Settings that will direct you to where you can learn more.

Aftermarket head units, especially equipped with Android, are still viable and powerful options that may sacrifice some conveniences with the benefit of increased control, transparency, and peace of mind when you turn on your vehicle.