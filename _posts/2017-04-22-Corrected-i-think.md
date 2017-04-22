---
layout: post
title: Corrected - I think
comments: True
tags: [CC2538, Kicad, RadioOne, DirtyPCB]
---
The new RadioOne board has arrived!
![RadioOne1]({{site.baseurl}}/assets/images/RadioOneFixed/DSC_5430.JPG)

![RadioOne1]({{site.baseurl}}/assets/images/RadioOneFixed/DSC_5416.JPG)

This time the board has the right CC2538 MCU footprint and the missing capacitor added. I have manually checked the board for shorts and the initial impression is that it seems just fine. Applying power made it possible for the debugger to attach to the MCU.

Next step is to test the 2.1V step-down converter and all the external connections.
Finally when all is proven OK, I will create the Board Support Package (BSP).
If anyone is interested, the Kicad project can be found on [github](https://github.com/SensorsUnleashed/RadioOne/tree/revA)
I will make a followup post, with the test result.

The following image is for size comparison.

![RadioOne1]({{site.baseurl}}/assets/images/RadioOneFixed/DSC_5433.JPG)
