---
title: "IPhone XS with no touch"
pageid: 4396
revid: 7444
kind: repair_guide
source: "https://repair.wiki/w/IPhone_XS_with_no_touch"
history: "https://repair.wiki/index.php?title=IPhone_XS_with_no_touch&action=history"
permalink: "https://repair.wiki/index.php?oldid=7444"
last_edited: "2025-06-07T17:15:48Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone XS"
  - "Stubs"
infobox:
  Device: "iPhone XS,"
  Affects_parts: "Motherboard"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope,Multimeter"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone XS with no touch

## Problem description
The iPhone turns on but touch doesn't work
![iPhone XS Touch FPC](images/8/85/Iphone_xs_touch_fpc.jpg)

## Symptoms
- Touch Doesnt work

## Solution
The most common issue on iPhone XS with no touch is a disconnection between the top and bottom boards, but in this guide we will go over diagnostic steps that should cover the main causes of no touch.

### Diagnostic Steps
The first step is to always try a known working screen to rule out bad parts.

Next do a visual inspection of the touch connector and surrounding components on the bottom board, check for any physical damage or liquid damage.

If there is no physical damage, the next step is to take diode readings of the FPC and compare with a known good value.

![iPhone XS Touch FPC Diode Values](images/0/0b/IPhone_Xs_touch_Diode_readings.png)

When taking diode readings of the FPC, if you measure a line that should read, for example, 0.500V but get 0.100V or 0.000V, it indicates a short on that line. The best way to trace the short is to inject voltage into the line with a DCPS and use a thermal camera to identify which component heats up.

If you measure a line that should read 0.500V but get OL (Open Line), it indicates a disconnection in the circuit. Don't assume there is a disconnection of the top board, there are many filters close by the touch FPC, use a boardview software like ZXW to trace where it goes. If the filter is OK then yes there is a problem between the top and bottom boards.

The main voltages needed for touch to work are:

PP5V25_TOUCH_VDDH_CONN

PP3V5_RACER_CONN

PP1V1_RACER_CONN

PP1V8_TOUCH_RACER_CONN

PP10V0_RACER_CONN

### Repair Steps
If you see any physical damage to the FPC, the solution is to replace it.

If there are any OL lines and the problem is not the filters split the boards and look for any ripped pads.
![Ripped Pads](images/e/e9/Ripped_motherboard_pad.jpg)
If you have ripped pads check check in a boardview software what they are for if they are ground they are not the cause of the issue.

If the ripped pad or pads you have are needed fallow this guide by REWA on how to repair a damaged pad. [https://www.youtube.com/watch?v=I_6xZVY7sFM]

Test the boards with a tool like and iSocket and see if touch is working if it is good all you have to do is to reball the bottom board and solder the baords back together (this is the most common issue on the XS with no touch)

![iSocket tool](images/1/1e/ISocket_tool.png)

If there are any missing voltages you need to trace to where they are generated and replace that component.

If any of the voltages above are missing replace U5600 (LM3373A2YKA)

## Final Testing
After reballing the motherboard test every function of the device,since a bad solder joint on a pad between the top and bottom boards can sometimes occur.

Make sure the device doesn't randomly reboot.
