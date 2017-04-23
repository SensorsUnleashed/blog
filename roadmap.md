---
layout: page
title: Roadmap
---

**This page will get updated every time a status changes or new things get added.**

*If you want the project to move in a specific direction, please share your thoughts.*

# Hardware

* ~~Get a cheap CC2538 radio module to get us started~~,
I found one at [Aliexpress](https://www.aliexpress.com/item/CC2538-module-CC2538-CC2592-ZigBee-high-Power-Module/32482311343.html?spm=2114.01010208.3.1.L3dFUs&ws_ab_test=searchweb0_0,searchweb201602_5_10152_10065_10151_10068_5100014_10136_10137_10060_10138_10155_10062_10156_10154_10056_10055_10054_10059_10099_10103_10102_10096_10148_10147_10052_10053_10142_10107_10050_10051_10171_10084_10083_10080_10082_10081_10110_10111_10112_10113_10114_10181_10037_10032_5110012_10078_10079_10077_10073_10070_10123_10124,searchweb201603_4,afswitch_1,ppcSwitch_4&btsid=d15fc965-562f-49e8-982d-8edf3f475c15&algo_expid=7b034ef3-735d-43f0-935f-65927b7e16c9-0&algo_pvid=7b034ef3-735d-43f0-935f-65927b7e16c9). I had to make a daughter board for it, which can be found [here](https://github.com/SensorsUnleashed/zb3219PA_XBEEAdapter)
* ~~Create test devices, to prove the concept.~~
3 devices were made:
  - [A Relay board](https://github.com/SensorsUnleashed/relayboard)
    - Toggle a relay
    - Sense if mains is there or not
    - If mains is lost, can maintain the network powered only from a cc2032 battery.
  - [A Pulse counting board](https://github.com/SensorsUnleashed/pulsecounter)
    - This board can count pulses. It is made, so that the [Optical Utility Meter LED Pulse Sensor](https://shop.openenergymonitor.com/optical-utility-meter-led-pulse-sensor/) from "OpenEnergyMonitor" can be used. I use it to monitor the energy consumption in our household.
  - [A mains detect board]()
    - The idea is basically to use existing installation to send out events in case power is applied or removed. A cc2032 battery is used to maintain the network and send out event when power is removed. It is possible to have it permanently powered from mains, while detecting a secondary line.
* Create our own CC2538 board
  * I made the [radioOne module](https://github.com/SensorsUnleashed/RadioOne), which is still in its testing phase.
* Temperature/humidity sensor
  * The schematic is in the workings
* Energy meter
  * I have bought the [MSP430i2040 Sub metering EVM](http://www.ti.com/tool/evm430-i2040s) which I think will work perfectly as a reference.
* Movement sensor (PIR)
* Create a border router.
  * In my day job I'm working on a board with the STM32F429 processor. Its a nice arm M4 processor, with build-in Ethernet and bus for external memory and LCD. I have already made it work with [contiki](http://www.contiki-os.org/), so it should be straight forward software wise to have it behave as a powerful border router. I plan on a board with 16MB of ram, LCD and Ethernet. Perhaps the cc2520 SoC for the radio part. This is only thoughts and are subject to change.

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
