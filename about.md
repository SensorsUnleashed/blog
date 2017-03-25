---
layout: page
title: About
---

<p class="message">
Im seeking people to help me making this project great. SW/HW/Mechanics/Documentaion etc. 
</p>

Sensors Unleashed tries to create a community driven sensor network. 

## What is the Sensors Unleashed network

So far 3 device types has been made:
* A mains detect device
* A Relay device
* A pulse detector

A device in the network can be paired with any another device available in the same network. 
Say you want to turn on the coffee machine when you turn on the lightswitch in the bedroom. This is done
by asking a mains detect device to send a message when the mains goes from off -> on. A relay device be
handling the power to the coffee machine. When the light is turned on the relay turns on the coffee machine, 
but not off when the light is turned off again.

The mains detect device know nothing about the relay device, and the relay device know nothing about the mains
detect device. The mains detecter knows that when is has an event, it has to transmit it to a list of attached devices.
All devices can handle the following events:
* Above
* Below
* Change

All devices can receive events from many and send out event to many.
There are no central controller handling the logics. This means, that any error in the network will be local to
the bindings that perticular device is attached to.

The setups is done through a gui tool, which knows of all the sensors. This tool is able to setup the bindings, and 
the levels for when to transmit a given event - a binding is stored in the the transmitting devices. The gui tool 
is only for setup - nothing is stored centrally.

All sensors can also be queried, if a polling scheme is more suitable for an application.
  