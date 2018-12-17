---
title: Zip Halo Gotchas
description: Common mistakes with the Kitronik Zip Halo
link: 
proglang: makecode
---

# Neill's Zip Halo Gotchas

## Software Gotchas

* **Most commands need to be followed by a "Show" command** before you see any change on the lights.  Commands that include the word "Show" will take effect immediately.
* You need to add the "neopixel" library (advanced: +extensions...) to makecode.
* You need to leave some time between commands such as "Rotate" so that your human eye can see what's been done, or else things will appear to blur together.
* "SetBrightness" only changes the brightness for colours created in future commands.
* The simulator won't show you differences in brightness. (But apart from that, USE the simulator - it's pretty good!).
* Set luminance to 50 when setting color using HSL.  With HSL (Hue, Saturation, Luminance), hue should be between 0-359, Saturation should be between 0-99, and luminance between 0-99 BUT as luminance goes beyond 50 it becomes white, regardless of the hue specified.  So a good luminance maximum is around 50.
* If the lights are wonky, multiple colours, perhaps the configured format is wrong. It should be the default, first one: "RGB (GRB format)". 
* The numbers (0 to 360) for "show rainbow" refer to the start and finish angle round the hues on a colour wheel.

## Hardware Gotchas

* The screws are electrical connections, not only mechanical.  They should be quite tight.
* There's a tiny switch on the zip halo, don't forget to turn it on!
* The 3xAAA (4.5v) battery pack should NOT be connected to the micro:bit as normal, but on the back of the halo near the bottom.
* Be careful to have kids support the battery when they pick up the zip halo, or the leads will get yanked out of the JST SH header.
* A 2xAAA (3v) battery pack is NOT recommended, though it may work initially.  It's particularly not recommended if you plan to use it with rechargeable batteries as these tend to have lower voltage.
* If you're asking for a rainbow and seeing red but not much green or blue the battery voltage has dropped too much.
