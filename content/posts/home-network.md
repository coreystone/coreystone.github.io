---
title: "Open-source routing and home network testing"
date: "2023-02-13"
description: "A quick dive into OpenWrt and iperf3 to test my home network's performance."
tags:
  - FOSS
  - networking
ShowToc: true
---

## Introduction

Gaining better control and visibility of my home network and its devices has always interested me since I happened upon [OpenWrt](https://openwrt.org/), a Linux operating system for network routing that can be installed on many embedded systems-- with a specific focus on consumer-grade routers. In this post, I discuss the selling points for my use case and test the performance of the OS versus that of my stock ISP router so I can understand the differences before diving deeper into managing my home network.

## Why consider a FOSS router?
This ultimately falls back to the age-old question: ["why FOSS?"](https://itsfoss.com/what-is-foss/) 

I'm choosing OpenWrt specifically because it supports a wide range of consumer-grade household routers, so it's perfect for my budget and needs. There's also an active community and continued development, so it's a very safe choice. See their list of [reasons to use OpenWrt](https://openwrt.org/reasons_to_use_openwrt).

Here are some features of OpenWrt that I'm specifically interested in for my home network:
* Improved performance & stability, which is what I will be testing later in this post
* Security:
	* Granular firewall settings (such as isolating IOT devices and controlling what devices can communicate with each other)
	* Recursive, encrypted [DNS over TLS](https://www.cloudflare.com/learning/dns/dns-over-tls/) via [Unbound](https://openwrt.org/docs/guide-user/services/dns/unbound)
	* Network-level VPN configuration
	* Network-level ad-blocking, such as [AdGuard Home](https://openwrt.org/docs/guide-user/services/dns/adguard-home)
* You can [back up and restore](https://openwrt.org/docs/guide-user/troubleshooting/backup_restore) if anything ever goes wrong
* It's free: in cost and from pre-installed vendor bloatware (it is Linux, after all)

{{< figure align=left src="/images/openwrt-logo.png" >}}
*via [openwrt.org](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fforum.openwrt.org%2Fuploads%2Fdefault%2Foriginal%2F3X%2F2%2F9%2F2965b316403db302c535cae40139e8c49bbad6e3.png&f=1&nofb=1&ipt=552fff3072cd943e3c181ffbb3c5e593d43628e15fe20bfd1ca550615c12edb3&ipo=images)*


Unfortunately, when it comes to OpenWrt compatibility, not all routers are built equal - with my ISP router included. So I had to buy a compatible model. In search of an ideal candidate that supported WiFi-6 and OpenWrt, I consulted the unrelenting source of all truth on the internet: reddit [/s](https://old.reddit.com/r/help/comments/hzc0oj/what_does_s_mean/). I spent a lot of time on the [r/OpenWrt sub](https://old.reddit.com/r/openwrt/) which inequivocally suggested the [Linksys E8450/Belkin RT3200](https://openwrt.org/toh/linksys/e8450)- also conveniently available at a Walmart near you! Oddly it is named differently in the US and Europe. So I purchased one and flashed OpenWrt onto it. This post is not going to be a tutorial about that. However, I'll provide the video guide that I followed if you're curious about the process:

{{< youtube id="MjS4tYzsGeo" image="/youtube/belkin-thumbnail.jpg" >}}

Beyond the juicy features mentioned above, which I will absolutely be implementing later on, I was curious about the veracity of OpenWrt's claims about improved performance and stability over routers running "vanilla" firmware:
> OpenWrt is designed by network professionals and others who care about the performance of their network and get the best throughput speeds and latency. OpenWrt incorporates many algorithms from recent research that perform far better than vendor-supplied firmware.

It purports to do so by designing the codebase around "low end hardware and maximum storage space", while boasting general Wi-Fi improvements and removing "vendor background processes and bloat", which includes additional software that you don't need and analytics for the vendor to collect more data about you and your device. Regardless of the OpenWrt's claims about speed or performance, these are all appealing qualities, so I would still venture to trying this out based on those perks alone.

As a disclaimer, this post focuses on the process of my labor rather than the outcome of it. Going into this, my only expectation and hope was to learn a few things along the way. And it's my blog, so in the words of an Eric Cartman, "I do what I want".

### What I'll be using
* Router flashed with OpenWrt
* [iperf3](https://github.com/esnet/iperf)
* Python 3
	* [iperf3 wrapper](https://pypi.org/project/iperf3/) for performing tests
	* [plotly](https://pypi.org/project/plotly/) for visualizing data
* Some phyiscal devices for wired and wireless testing (laptops, desktop) - there are also FOSS mobile apps on [iOS](https://github.com/ndfred/iperf-ios) and [Android](https://github.com/davidBar-On/android-iperf3/)

## What is iperf3?
iperf3 is a tool that measures network performance and stability. It is a lightweight, open-source program that runs in the command-line and uses the [client-server model](https://en.wikipedia.org/wiki/Client%E2%80%93server_model) to conduct tests. That is, an iperf server is created on an IP:port pair and waits for a client configured with some arguments to connect to it on that port. Clients have multiple parameters that can be used for different types of tests.

The different parameters offered by iperf3 allow us to test with TCP segments and UDP datagrams, which can provide different insights about the network. For both my wired and wireless devices, I'll be testing for network bandwidth over TCP, and over UDP, for bandwidth, jitter, and packetloss.  This will give me a good glimpse at the switching and routing performance for the ISP and Belkin routers. This will also enable me to look at how well multiple clients share the bandwidth. This is the goal of WiFi 5 (802.11ac)'s [MU-MIMO](https://www.cisco.com/c/en/us/products/wireless/what-is-mu-mimo.html) (multi-user, multiple input, multiple output), which basically tries to ensure that the channel is distributed reasonably evenly amongst all connected clients so that no one client hogs it.

This has all been neatly wrapped into a neat Python 3 library that can allow us to enter iperf3 commands programmatically, and, more importantly, extract and analyze the resulting data. This data can be exported as a .json file, or, more conveniently, parsed within the program itself. Overkill? Yes. An interesting idea with the prospect of learning a few things along the way? Also yes.

## The library and approach
The approach and inspiration for this post is largely credited to YouTube user [@OneMarcFifty](https://www.youtube.com/@OneMarcFifty), who has been a big influence in leading me to poke my head into homelabbing and managing my own home network. His testing process can be seen in this video, which coincidentally also piqued my interest in OpenWrt: 

{{< youtube id="a4fDwG3aEb8" image="/youtube/xiaomi-4a-thumbnail.jpg" >}}

I am going to run iperf3 on multiple physical devices that I can position around my house to test their wireless strength. This is a pretty manual and brutish way of doing things, granted, but it works for my goals; it will also give me a good insight of how [beamforming](https://www.networkworld.com/article/3445039/beamforming-explained-how-it-makes-wireless-communication-faster.html) and MU-MIMO work in my home. In the future, I'd love to see if I could speed things up by [containerizing iperf3](https://hub.docker.com/r/networkstatic/iperf3/) with Docker.

Before doing anything, we need to do the following on all client and server machines:
* Install [iperf3](https://iperf.fr/iperf-download.php#windows)
* Install [Python3](https://www.python.org/downloads/)
* Install and import the the Python [wrapper library](https://pypi.org/project/iperf3/): `import iperf3`

This wrapper is pretty simple. We have two classes, which align with the client-server model that we're following: `Client` and `Server`. Each class ojbect requires a few arguments first before running a test and both return a `TestResult` object when a test is complete. This test result is what we'll be using to extract interesting data.

A Client object binds itself to a Server by targeting the server's IP and port number. This client-server duo is established over a single port, so multiple clients must be bound to multiple corresponding servers. Both Client and Server return the results of a test (as a TestResult object) when done. I am going to grab the client-side results, as it turns out that I will *only* be able to grab the client-side results: it seems that it is impossible to create multiple concurrent servers in Python and is only possible in the command line. This is an unfortunate limitation-- that could have a workaround-- but will only be an inconvenience. I will create those multiple servers in the command line with: `iperf3 -s <port> -D` (where `-D` means "daemon") and then code out the clients. By the way, to create a client in the command line, enter: `iperf3 -c <server_ip> -p <port>`

{{< figure align=left src="/images/approach_diagram.png" >}}


### Coding the server
So to get started, I need to configure the server. All this entails is creating the object, hooking up its IP and port, and running it infinitely while it waits for clients to connect to it.
```
server = iperf3.Server()         # Initialize the Server object
server.bind_address = 'x.x.x.x'  # IP4 address of the machine
server.port = 5201               # Default port for iperf3
while True:                      # The server will run until you tell it to stop
	server.run()
```

### Coding the client
Like with the server, we have some initial setup to handle.
```
client = iperf3.Client()            # Intialize the Client object
client.bind_address = 'x.x.x.x'     # Tied to the machine's IP
client.port = 5201                  # Default port for iperf3
client.server_hostname = 'x.x.x.x'  # Identify the server to connect to
```
Here is where things get more interesting, as Client objects have more parameters to adjust what kind of tests are run and how. Here are the parameters I will be using:
 ```
client.duration = 30           # Number of seconds the test is run for
client.bandwidth = 1000000000  # 1 Gbps (that's nine zeroes)
client.protocol = 'udp'        # For changing between TCP segments and UDP datagrams ('tcp' is the default)
```
Here are some optional parameters that also might be interesting to explore, but for my purposes I won't be tinkering with them. 
```
client.num_streams = 10  # Allows you to get closer to maximum throughput if that's something you need
client.zerocopy = True   # Avoids unnecessary data copying to reduce CPU load on sender (per Wikipedia)
client.reverse = True    # Causes the server  to send packets to the client (by default, False: client sends traffic to server)
```

Note: if you just want to see the output of the test in the console (how iperf3 behaves normally), just disable JSON test results: `client.json_output = False`. Disabling verbosity via `client.verbose = False` will reduce the noisiness of the output by only displaying the final result.

## Test 1: Switching between wired devices
I'll be starting things off nice and easy. One server and one client on a wired Ethernet connection will allow for testing the switching performance of the router. Start the server (in a `while` loop) and prep the client.

The client begins in the same way as the server: with the `.run()` function. Save the returned output of that test to a variable: `result = client.run()`

From here, we can select specific values from the output using the object's attributes ([listed the official documentation](https://iperf3-python.readthedocs.io/en/latest/modules.html#testresult)) to automatically parse the JSON for us.

I show the console output from my terminal in Ubuntu for clarity. Running the test in Python yields more or less the same result for both TCP and UDP. My hope is that this gives a baseline to compare against wireless performance (with multiple devices).

here are my data results (dont graph yet)
explain

## Test 2: Routing between wireless devices
First, I'll do a wireless test between a single client and server to set some sort of baseline to refer to. The following screenshot shows my console output:

{{< figure align=left src="/images/wired_tcp_udp_console.png" >}}


* Over TCP, the bitrate varies between 100-200 Mbps
* Over UDP, the bitrate is at 1Mbps the whole time, with minimal jitter and no packet loss
	* *But what is jitter?* An informative [article by agora.io](https://www.agora.io/en/blog/jitter-vs-latency/) gives a high-level intro as follows:
		* "[As data is transmitted across a network, it's] broken down into packets and sent to the receiver at evenly-spaced intervals. Upon arrival at their destination, the packets are reassembled. In smooth communication, data packets flow consistently and arrive at their destination in the correct order. However, data packets sometimes arrive late or out of order due to network congestion or occasional rerouting. The **variation in this latency or delay of the transmission** is referred to as jitter [...] High jitter denotes a significant variation in latency, whereas low jitter represents only minor changes"
		* Additionally, for context, "jitter of *30ms or less* is generally regarded as acceptable"
	* *How does it differ from latency (ping)?*
		* Team Agora notes that latency "is the delay in transferring data to a given network destination" while jitter is "the variation within that delay" 
	
* I used the -R argument for both TCP and UDP to get another set of data to compare against. To achieve this in Python, set: `Client.reverse = True`

Okay, now for running the 3 clients at the same time to see how they interact:

{{< figure align=left src="/images/wireless_mimo_tcp_udp.png" >}}

* Jitter significantly increases (relative to its original state) - although barely cracking 1 millisecond, so it's still pretty minimal

* The bitrate hovers between 150-200 Mbps, and the aggregate shared bitrate between all 3 devices consistently floats around there
* UDP seems largely unaffected besides jitter
* The `Cwnd` for client #2 in the middle is high, meaning....? Well, I had to do some reading on this and found an excellent [article by StackPath](https://www.stackpath.com/edge-academy/what-is-cwnd-and-rwnd/) which reads:
	* The "**Congestion Window (cwnd)** is a TCP state variable that limits the amount of data the TCP can send into the network before receiving an ACK. The **Receiver Window (rwnd)** is a variable that advertises the amount of data that the destination side can receive. Together, the two variables are used to regulate data flow in TCP connections, minimize congestion, and improve network performance"
	* [Wikipedia elaborates](https://en.wikipedia.org/wiki/TCP_congestion_control#Congestion_window): "The congestion window is maintained by the sender and is a means of stopping *a link* [such as an intermediary router] between the sender and the receiver from becoming overloaded with too much traffic"


As OneMarcFifty astutely describes in his video on the Xiaomi 4A, what's most important is not the actual bitrate (as it's already sufficient for the needs of my home network), but rather that the bitrate is being equally shared amongst these devices (instead of one device hogging the whole channel). I would say that both routers accomplished this, with the Belkin RT3200 doing the job even better.


## Graphing/visualizing the results 
To turn all these boring numbers into pretty pictures, I'll be using the [Plotly graphing library](https://plotly.com/python/). Following the official documentation for [bar charts](https://plotly.com/python/bar-charts/) and [histograms](https://plotly.com/python/histograms/), I was able to familiarize myself enough with the library make some visuals that barely pass as charts. I used both bar charts and histograms, probably incorrectly, just to explore more of the library. Again: my blog, I do what I want.

I was able to test my ISP router and the Belkin RT3200 with its factory image, so I will be plotting the data for those devices and filling in random *placeholder* data for the Belkin RT3200 with OpenWrt for now.

Let's start with a simple bar chart:`import plotly.express as px`

I want to create a bar chart comparing the wired bitrate between devices using `px.bar`:

```
fig = px.bar(x=["ISP (Factory)", "Belkin RT3200 (Factory)", "Belkin RT3200 (OpenWrt)"], y=[96, 92, 99], 
                 title="Avg. Wired Bitrate (Mbps)")	# where y[n] is the bitrate for each router
```

After filling in the data, you can customize the "layout" of the chart:
```
fig.update_layout(
	title_text='Bitrate among wired iperf3 clients',  # title of plot
	xaxis_title_text='Router, Image',                 # x-axis label
	yaxis_title_text='Bitrate (Mbps)',                # y-axis label
    )
```
Here is the result. Shout out to Daniel Gehrer ([xa1.at](https://xa1.at/)) for the [shortcode to embed HTML in Hugo](https://xa1.at/hugo-include-html/) to display everything.


{{< include-html "/static/wired_bitrate.html" >}}

And now for a histogram: `import plotly.graph_objects as go`

I'll compare the wireless bitrate for each of the 3 test devices on the routers tested. First enter the data, creating a list for each device and also a list of the routers:
```
routers = ["ISP (Factory)", "Belkin RT3200 (Factory)", "Belkin RT3200 (OpenWrt)"]
    device_1_values = ["47.7", "117", "42.5"]
    device_2_values = ["46.2", "73.1", "50.5"]
    device_3_values = ["100.7", "52.3", "44.2"]
```
Plot the data by creating a `Figure` and adding a "trace" for each router:
```
    fig = go.Figure()  # programmer humor
    fig.add_trace(go.Histogram(histfunc="sum", y=device_1_values, x=routers, name="Client 1"))
    fig.add_trace(go.Histogram(histfunc="sum", y=device_2_values, x=routers, name="Client 2"))
    fig.add_trace(go.Histogram(histfunc="sum", y=device_3_values, x=routers, name="Client 3"))
```

Here is the result:
{{< include-html "/static/wireless_bitrate_shared.html" >}}


{{< include-html "/static/wired_bitrate_tcp_udp.html" >}}


{{< include-html "/static/avg_jitter.html" >}}


## Some final thoughts
Due to the nature and limited extent of the testing, I'm not sure I can make any real conclusion about the difference in performance between routers, but the results seem to slightly favor OpenWrt, which makes sense given the lightweight and debloated nature of the operating system. Performance improvements would likely have been more noticeable in more strenuous or specialized scenarious, like with a meshed network. At the very least I can say that I feel more confident in testing my network and have another tool in my toolbelt for the future. 

As I mentioned before, my bitrate was already more than enough, so scoring WiFi 6 and some extra range from the Belkin RT3200 makes me a happy camper regardless of the outcome. However, the main impetus for me was to move to an open-source, privacy-respecting and empowering solution to manage my network, and now I can enjoy all the benefits that come from that.

Was aggregating and plotting all this data in Python necessary? Definitely not, but it made for a good challenge and I learned a lot from it, which will be a recurring theme throughout this blog. 

### Resource dump
* [Wikipedia -- OpenWrt](https://en.wikipedia.org/wiki/OpenWrt)
* [Plotly docs -- Bar Charts](https://plotly.com/python/bar-charts/)
* [PyPI -- iperf3](https://pypi.org/project/iperf3/)
* [GitHub -- iperf3](https://github.com/thiezn/iperf3-python)
* [iperf3 examples](https://iperf3-python.readthedocs.io/en/latest/examples.html)
* [TCP Slow Start](https://www.keycdn.com/support/tcp-slow-start)
* [IBM iperf tutorial](https://www.ibm.com/support/pages/how-do-you-use-iperf)
* [Wikipedia -- Zero-copy](https://en.wikipedia.org/wiki/Zero-copy)
* [OneMarcFifty -- Xiaomi 4A script](https://github.com/onemarcfifty/xiaomi_4a/blob/main/README.md)