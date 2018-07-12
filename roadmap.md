---
layout: page
title: Roadmap
---

**This page will get updated every time a status changes or new things get added.**

*If you want the project to move in a specific direction, please share your thoughts.*

# Hardware
---------
**DONE**

*Get a cheap CC2538 radio module to get us started*

I found one at [Aliexpress](https://www.aliexpress.com/item/CC2538-module-CC2538-CC2592-ZigBee-high-Power-Module/32482311343.html?spm=2114.01010208.3.1.L3dFUs&ws_ab_test=searchweb0_0,searchweb201602_5_10152_10065_10151_10068_5100014_10136_10137_10060_10138_10155_10062_10156_10154_10056_10055_10054_10059_10099_10103_10102_10096_10148_10147_10052_10053_10142_10107_10050_10051_10171_10084_10083_10080_10082_10081_10110_10111_10112_10113_10114_10181_10037_10032_5110012_10078_10079_10077_10073_10070_10123_10124,searchweb201603_4,afswitch_1,ppcSwitch_4&btsid=d15fc965-562f-49e8-982d-8edf3f475c15&algo_expid=7b034ef3-735d-43f0-935f-65927b7e16c9-0&algo_pvid=7b034ef3-735d-43f0-935f-65927b7e16c9). I had to make a daughter board for it, which can be found [here](https://github.com/SensorsUnleashed/zb3219PA_XBEEAdapter)

---------
**DONE**

*Create a Relay board, so that we can toggle some things on and off.*

The [Relay board](https://github.com/SensorsUnleashed/relayboard) has been made and testet. Only thing missing is the ability to maintain the radio when no mains is applied. This is something I consider for a power conservation task later on.

    It can:
      - Toggle a relay
      - Sense if mains is there or not
      - (**PENDING**) If mains is lost a cr2032 battery help power the device so that it can keep maintaining the network and improve responsivness.

-------------
**DONE**

*Create a Pulse counting device*

The purpose of the [Pulse counting board](https://github.com/SensorsUnleashed/pulsecounter) is to count the light pulses on the power meter placed on our house by the energy company.

    It can:
    - Count 0-5V pulses. It is compatible with the [Optical Utility Meter LED Pulse Sensor](https://shop.openenergymonitor.com/optical-utility-meter-led-pulse-sensor/) from "OpenEnergyMonitor".

---------
**DONE**

*Create a [Mains detect board]() that detects if power is switched*

The sole purpose of this project is basically to convert various physial actions to events in our system. The idea for this device is basically to use existing installations to send out events in case power is applied or removed. It is possible to have it permanently powered from mains, while detecting a secondary line.

    It can:
    - Detect if mains is present or not.
    - (**PENDING**)If mains is lost a cr2032 battery help power the device so that it can keep maintaining the network and improve responsivness.

-------------
**DONE**

*Create our [own CC2538 board](https://github.com/SensorsUnleashed/RadioOne).

Its perfectly fine to use pre-fabricated radio modules, but for how long will they keep produce those? To keep prices low, form factor small and delivery time short its better to have our own radio. I have decided to have the form factor like the XBee. This way it's my hope that we can use some of the projects made for that platform for expanding ours as well.

    It can:
      - Communicates on 2.4GHz using a 6Lowpan (802.15.4) radio.
      - Has 4 LEDs for debugging and signalling what ever is needed.
      - Uses a 10 pin debug interface to use directly or with our testboard (See ...).

--------------
**PENDING**

*Create a [Temperature/humidity sensor]().*

It would be nice to be able to measure those things. If we for instance want to know when the temperature in the shed goes below 6C, and use the event for turning on a heater. This will allow us to keep paint and vegetables that don't like frost.

Current status:
  * The schematic is in the workings
  * I have experienced with some I2C chips which seems qiute good. If I want a high resolution with little error they become rather expensive.
  * I am looking into building a PT100/PT1000 board.

------------
**PENDING**

Build a Energy meter.

Measuring the energy consumption of a device will make us capable of detecting when its turned on or off, its CO2 footprint, cost etc. and based on those numbers initiate various actions around the house.
To save standby current an idea could be to completely shut down the supply to the TV/Stereo when you turn on the light after 10pm - but only if the TV/Stereo is not in use.

Current status:
  * I have bought the [MSP430i2040 Sub metering EVM](http://www.ti.com/tool/evm430-i2040s) which I think will work perfectly as a reference.
  * I have made a preliminary schematic.

-----------
**PENDING**

Movement sensor (PIR)

A nice way to interact with the system is when the system it self senses what to do. This is something the PIR sensor can do.
Where I live, during the summer, many people spend time in the garden. It would be nice to have you phone vibrate or sound when someone entering the front door. This could make us more safe without having to lock the front door.

I have bought some modules from aliexpress, but haven't had the time to test those yet.

-----------
**PENDING**

Create a border router.

In my day job I'm working on a board with the STM32F429 processor. It's a nice arm M4 processor with build-in Ethernet and bus for external memory and LCD. I have already made it work with [contiki](http://www.contiki-os.org/), so it should be straight forward software wise to have it behave as a powerful border router. I plan on a board with 16MB of ram, LCD and Ethernet. Perhaps the cc2520 SoC for the radio part. This is only thoughts and are subject to change.

----------
# Software
## Embedded
* ~~Setup the [contiki](http://www.contiki-os.org/) environment~~
* Enable [CoAP](http://coap.technology/) and create a standard for communicating with each device
  * This work has started and for the most part done. The protocol is still subject for change
* ~~Create the pairing mechanism~~
* ~~Create the event mechanism, so that events are fired at the time specified in the configuration~~
* Create the event receive mechanism for a device. What should happen when e.g. a device receives an "above event", the device should in a standard way post its capabilities and the GUI should then set it up.

## High Level
* ~~Create a GUI tool that can test functionality and pair devices~~
* Have the GUI tool work in Windows. For now it runs in a Linux environment.
* Create examples for the test devices.
* Create a graph tool to monitor the devices in the network. I figure a tool that monitors the household consumption with the pulse sensor, and marks on the plot when events are detected in the network (lights turned on/off, coffee machine etc.) The tool is only for demonstration purposes. I think I will make it in node.js or python.
* Port to android/ios

## Common
* Make the setup easier to get going for new contributors.
* Secure the communication - from .

# Documentation
* Create documentation for how to setup the environment and what tools to use
* Document each test sensor. What is the intention with it, how is it made, what can be done etc.
* Document various use cases for Sensors Unleashed - supply illustrations

# Marketing
* ~~Create a landing page~~
* ~~Create a blog~~
* Ask people with shared interests to get involved. Supply them with hardware if necessary.
* When the radioOne board is fully tested, put it on [Tindie](https://www.tindie.com/)
* Put the zb3219PA daughter board on [Tindie](https://www.tindie.com/)
* Make the project meet the requirements of the [Contiki OS](https://github.com/contiki-os/contiki/wiki/Code-Contributions#new-platforms).
