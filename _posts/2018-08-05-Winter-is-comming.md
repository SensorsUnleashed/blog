---
layout: post
title: Winter is comming
comments: True
tags: [3D Printing, FreeCad, OpenSCAD]
---

Its been a while since my last post but I have been busy getting all the basics done. Made the [Wiki](https://github.com/SensorsUnleashed/Link/wiki) up to date, created a twitter account for the project and doing a lot of software.

The [radioOne](https://github.com/SensorsUnleashed/Link/wiki/RadioOne-Ver-1) has proven to work flawlessly. I'm using that exclusively in all the devices currently installed in my own home.

I also bought a Ultimaker 2+ extended, so that I could print some nice casings when needed - an example is [Pulse Counter](https://github.com/SensorsUnleashed/Link/wiki/Pulse-Counter). Getting the 3D printer was the easy part, getting to know FreeCad and openSCAD was entirely different. I'm still not an expert, but I'm getting there. At least now I can make what ever I need without googling all the time.

Software wise I have made a number of improvements to the code. One of the big steps was the possibility to upgrade the firmware. This is nice because, I don't need to power down any of the radios, but instead simple sit at my desk and remote upload the firmware wirelessly. I will blog about how I made this soon.

A lot of performance upgrades has been made to how the CoAP bindings are handled. In sensors unleashed a device can be paired to a number of other devices. If you remove a device, the system needs to keep the binding till there is no more devices using it. A lot of corner cases like this has been handled and it has proven to be very stable.

Another issue that has been addressed is the case where power is lost to a device with a link to it. En example - a button is linked to a relay, but power to the button is lost. Normally its the relay that will be subscribing to the button, but it still thinks its attached. A mechanism for handling this has been made and a blog post will come soon around this issue and the considerations I made.

Anyway, thanks for listening.

Winter is coming - and soon it will be getting darker here at the north which means more time for Sensors Unleashed :-)

See ya!
