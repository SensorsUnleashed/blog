---
layout: post
title: Introducing the Sensors Unleashed network
comments: True
tags: [Contiki, Hardware, Info]
---

I have long had the urge to measure and control various parts of my life, house and garden, but haven't been able to find any solution that really suited my needs. I had a lot of different criterias, but the 4 listed below was mandatory.
* Open Source:  
I have seen too much closed source software, that because of time to market the developers had to cut too many cornes regarding safety, structuring, bugfixing etc. I dont want that - not even for free :-)
* Open Hardware:    
I like working with kicad and layout my own boards. To be able to open up a already made design and change it to my needs would be SO nice! What good is open hardware if the software used for editing costs 8000$....
* Open standards  
I, ofcourse dont want to buy any product, which uses undocumented communication and where the only way to get data is by reverse ingeering the protocol - such waste of time. The standards used should be readaly available for download without any pay-wall.
* Community driven  
The most innovative ideas comes from people acutally using a product. This is the part most companys dont get. I would love to work with a project, where products are made based on specific needs and interest of its users. Not the other way around.

All the listed criterias made me jump into creating my own network - [Sensors Unleashed](www.sensorsunleashed.com).

## What is the Sensors Unleashed network

The Sensors Unleashed project, is work in progress, and will hopefully continue that way :-) The functionality described here, is already working, but still has a few rough edges.

The network consists of a growing number of devices - all made by my self.

### How is it working

A device in the network can be paired with any another device available in the same network.
Say, you want to turn on the coffee machine when you turn on the lightswitch in the bedroom. This is done
by asking a mains detect device to send a message when the mains goes from off -> on. A relay device are handling the power to the coffee machine. When the light is turned on, it gets notified and the relay turn on the coffee machine, but not off when the light is turned off again.

The mains detect device know nothing about the relay device, and the relay device know nothing about the mains
detect device. The mains detecter knows that when it has an event, it has to transmit it to a list of attached devices.
All devices can handle the following events:
* Above
* Below
* Change

All devices can receive events from many and send out event to many.
There are no central controller handling the logics which again removes the "single point of failure" problems that central controllers has.

The setups is done through a gui tool, which knows of all the sensors. This tool is able to setup the bindings, and
the levels for if and when a device will transmit a given event - a binding is stored in the the transmitting devices. The gui tool
is only for setup - nothing is stored centrally.

All sensors can also be queried, if a polling scheme is more suitable for an application.

Last but not least, the communication between the devices is handled by 6LowPan in a mesh typology which means, that if any device strugles with weak signal pathes, a device placed midway will boost the signal. This way, the network can have the best range, but with a lower throughput.

### Hardware
So far 3 device types has been made and 2 radios:

Devices:
* [A mains detect device]()
* [A Relay device](https://github.com/SensorsUnleashed/relayboard)
* [A pulse detector](https://github.com/SensorsUnleashed/pulsecounter)

Radios
* [Radio One (Newest)](https://github.com/SensorsUnleashed/RadioOne)
A Texas CC2538 based radio module using the XBEE connection footprint. This is the first module entirely home made. The board is not yet ready, but will be soon.  
* [XBEE Adapter for the zb3219PA](https://github.com/SensorsUnleashed/zb3219PA_XBEEAdapter) module (First cheap china module)  
This was the first module I made. I found the module on aliexpress, and made a adapter board for it in kicad. This board works very well, but is a bit large compared to the Radio One. It has excelent range, and is pretty cheap.


### software
I have been using the [Contiki OS](http://www.contiki-os.org), which is now up in version 3.0. It is nicely structured and easy to get going. Besides, it has already really good support for the Texas CC2538 tranciever.

All wireless communication to and from the device nodes is done using the CoAP protocol, and the transmission scheme is done as described in the concept description above.


Please comment or ship me a mail, if you find this project inspiring and want to help.

Ole Nissen
