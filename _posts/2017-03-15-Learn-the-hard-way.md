---
layout: post
title: Learn the hard way
comments: True
tags: [CC2538, Kicad, RadioOne, DirtyPCB]
---
I guess, not all in a project is a success. This post is about one of those times:-)

A few weeks back, I finally had the time to finish a PCB for the CC2538 based radio, named the RadioOne. I stayed up late, and was quite happy with the result, so I went along and ordered 10 prototypes from DirtyPCB which arrived about 2 weeks later.

I immediately started soldering the board, using a frying pan and an infrared temperature meter. I was quite happy with the result.

![Here is the assembled board]({{site.baseurl}}{{site.url}}/assets/images/RadioOneMistake/DSC_5405_small.JPG)

 but.... I noticed that the QFN package of the MCU didn't flow as well into place as I had hoped. First I thought that it was because its a harder component to solder - a QFN package is not made for hand soldering. Well, I finished placing all the components, but the MCU had practically all its legs shorted. But why!!! Ok, i must have put to much solder paste on, so I used the airgun to blow off the chip again. Hmm, everything looked ok. Then I tried placing it again. Still no good. Then I opened up KiCAD and had a look at the footprint - and then it hit me.... At the time, when I first created the schematic, I looked up a QFN package with 56 pins, and found one. It looked just right, so I picked that one. I told my self, that I would double check later, but I forgot.. It turns out, that the footprint I used was 7x7mm instead of 8x8mm. The pitch should be 0.5mm, but was 0.4mm. That explains it all - but let me tell you - right there it didn't feel right :-(

The same day, I created the footprint my self according to IPC and rerouted the board. Hopefully the new board will arrive in a few days from now.

I will let you know how it went.

Here is a photo for size comparison

![RadioOne size]({{site.baseurl}}{{site.url}}/assets/images/RadioOneMistake/DSC_5408_small.JPG)
