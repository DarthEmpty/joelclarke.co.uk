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

Eventually, enough was enough. After a little digging, my friend discovered that the wifi card itself was the issue. This was confirmed after I then researched the different WLAN standards and noticed that some were better equipped to deal with Google Wifi than others.

These standards were made by the [Institute of Electrical and Electronics Engineers (IEEE)]. Since their first WLAN standard,  802.11, was created in 1997, IEEE have gone through many iterations of standards - each one aiming to be an improvement on the previous one. If you want to find out more about the different standards and their progression, I would recommend [this blog post].

The standards that I became most interested in, however, were 802.11n and 802.11ac. 802.11ac was made to be an improvement over 802.11n, utilising **dual-band wireless technology**. This allows for an 802.11ac compatiable device and an 802.11ac compatiable router to maintain 2 connections of different bandwidths at the same time.

By calling the command `sudo lshw -c network` on Ubuntu, I found out that my old wifi interface was a `BCM4352 802.11b/g/n Wireless Network Adapter`, meaning that my old wifi card was 802.11b/g/n compatiable (making it an 802.11n card). Because one of Google Wifi's features is dual-band wifi which is a feature of the 802.11ac standard, I figured that it would be a good idea for my new wifi card to also be 802.11ac compatiable. And so, I looked around on eBay for the cheapest, nearest, 802.11ac compatiable wifi card I could find.

It's odd though, Google states that Google Wifi is capable of *Simultaneous dual-band Wifi (2.4 GHz/5 GHz) supporting IEEE 802.11a/b/g/n/ac* (This can be seen [here] under the *Connectivity* section). That implies that my old wifi card should have been OK because of the backwards compatiablity that Google Wifi offers. Regardless, after buying the new wifi card (and a couple more hiccups that I'll tell you about next), the *Heroes of the Storm* became a lot less frustrating to play.

## A Sizeable Mistake

I was very excited when my brand new wifi card came in the post. So much so that I rushed to install it in my laptop as soon as it came through the door. However, that excitement soon came to a grinding hault when I discovered that the card that I wanted to install was a different size to the card I was going to replace.

I later discovered that I had ordered an 802.11ac card of the wrong **form factor**. The form factor is a feature of all hardware that determines it shape and size and, by extension, what other hardware components it's compatiable with. The form factor that the wifi card had to be in order to fit my laptop was *Mini PCIe (half height)*. The form factor that I bought was *M.2 (half height)*. Underneath are the said wifi cards, with Mini PCIe first and M.2 second.

![A Mini PCI Express Wifi card (half height)](/assets/images/mini_pcie.png)

![An M.2 Wifi card (half height)](/assets/images/m2.png)

So, unfortunately, I had to spend more money than I was expecting to in getting the correct wifi card for my laptop. And, unfortunately, this would not be the last bit of trouble I had to deal with...

## Driven Mad by Drivers

[Google Wifi]: https://store.google.com/product/google_wifi
[Institute of Electrical and Electronics Engineers (IEEE)]: https://www.ieee.org/
[this blog post]: https://www.lifewire.com/wireless-standards-802-11a-802-11b-g-n-and-802-11ac-816553
[here]: https://store.google.com/product/google_wifi_specs
