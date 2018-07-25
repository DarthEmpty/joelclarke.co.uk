---
layout: default
---

A while ago, a friend of mine bought [Google Wifi] and started using it as the main wifi router in his house. Both of us being major Google fans, we were very excited about seeing and using such cutting edge technology.

My laptop, on the other hand, was not...

The rest of this post is about the long, arduous journey that I ventured on in order to make my laptop and the router agree with each other - perhaps it might help you to avoid having to spend as much time on it as I did.

## My Laptop, DMO

I have a Dell Precision M4700 named *DMO* (Inspired by the cartoon character: *BMO* from *Adventure Time*). It's a chunky workstation that's designed to be easily moddable. Since I've bought it, I've replaced the CD Drive with a second SSD and installed a bluetooth module, and I was surprised at how easy the process was both times. It's also worth noting that I have both Windows 10 and Ubuntu 16.04 installed on DMO where both Operating Systems occupy different SSDs.

I love DMO to bits but we've come across our fair share of troubles - which is probably bound to happen when you buy an outdated second hand laptop off of eBay... :sweat_smile: For example, prior to having a bluetooth module, I went round the houses playing with DMO's wifi switch to try and activate bluetooth on the laptop. It wasn't until I took a glance inside after several days and noticed a small lid to a compartment labelled *Bluetooth Module* that I wondered to myself *"Hey, maybe I need one of those..."*

DMO's interactions with Google Wifi brought another issue to light. It seemed that, after connecting to the router, everything would work well for a few moments until the connection just dropped out. Said connection wouldn't be restored until I actively disabled and re-enabled wifi from the laptop which lead to the connection dropping out again, and so on. This would happen annoyingly often when playing the PC game: *Heroes of the Storm* - a game that's very reliant on a stable internet connection. There were incidents where I was penalised for disconnecting from the game because of DMO's petty disagreements with Google Wifi. :roll_eyes:

## The Root of the Problem - Wifi Standards(?)

Eventually, enough was enough. After a little digging, my friend discovered that the wifi card itself was the issue. This was confirmed after I then researched the different wifi standards. The discussions that I read about the most were between the 802.11n and 802.11ac standards.

There are many wifi standards and, if you're interested in them, I would check out [this blog post].

My old wifi card was 802.11b/g/n compatiable (making it an 802.11n card). Because one of Google Wifi's features is dual-band wifi which is a feature of the 802.11ac standard, I figured that it would be a good idea if my new wifi card was also 802.11ac compatiable. And so, I looked around on eBay for the cheapest, nearest, 802.11ac compatiable wifi card I could find.

It's odd though, Google states that Google Wifi is capable of *Simultaneous dual-band Wifi (2.4 GHz/5 GHz) supporting IEEE 802.11a/b/g/n/ac* (This can be seen [here] under the *Connectivity* section).

## A Sizeable Mistake

## Driven Mad by Drivers

[Google Wifi]: https://store.google.com/product/google_wifi
[this blog post]: https://www.lifewire.com/wireless-standards-802-11a-802-11b-g-n-and-802-11ac-816553
[here]: https://store.google.com/product/google_wifi_specs
