---
title: "Surface Pro 4 does not turn on"
pageid: 4161
revid: 7139
kind: repair_guide
source: "https://repair.wiki/w/Surface_Pro_4_does_not_turn_on"
history: "https://repair.wiki/index.php?title=Surface_Pro_4_does_not_turn_on&action=history"
permalink: "https://repair.wiki/index.php?oldid=7139"
last_edited: "2025-05-27T21:30:43Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Surface Pro 4"
  - "Stubs"
infobox:
  Device: "Surface Pro 4"
  Affects_parts: "Motherboard"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Surface Pro 4 does not turn on

## Problem description
The device does not turn on.
![Example of blow resistor on a Surface Pro 4](images/8/8d/Blow_resistor.png)

## Symptoms
- The device doesn't turn on.
- The device doesn't turn on after a battery replacement.

## Solution
If your device stopped turning on after a battery replacement, it is highly likely that a component on the motherboard has failed (I discovered this the hard way).

To fix the device, we will perform a few troubleshooting steps.

### Diagnostic Steps
There are 3 components that commonly fail: a 0-ohm resistor, two diodes, and the PMIC.

First, let's check the 0-ohm resistor. Below is an image showing where this component is located. Using your multimeter in resistance mode, measure the resistance, it should be 0 ohms. If you measure anything different, the component is faulty.

![Surface Pro 4 Resistor Location](images/f/f8/Surface_pro_4_resistor.png)

The next two components to check are the two diodes. Using your multimeter in continuity mode, ensure they don't have continuity across them. Also, verify there is no physical damage, such as cracks or holes.

![Surface Pro 4 Diodes Location](images/3/3e/Surface_pro_4_diodes.png)
The next component to check is the PMIC. This component is commonly shorted. Follow the image below.
![Surface Pro 4 PMIC](images/6/61/Surface_Pro_4_PMIC.png)

If one of the lines is shorted inject 1V with a DCPS and you will likely see the PMIC hot under a thermal camera.

### Repair Steps
The resistor is easy to replace. Use a hot air station to desolder the old one and solder a new one, or if you have hot tweezers, it's even easier.

The diodes follow the same process as the resistor.

The PMIC is a BGA chip. To remove it, use your hot air station, clean the pads of any old solder, and solder a new PMIC.

When assembling the device, be careful because the battery is always providing power to the motherboard. I recommend installing all the shields you can and being cautious with the heat sink, as it is made of copper, any wrong touch on a component can damage the motherboard again.

## Final Testing
Ensure the device charges and turns on. Test all other functions of the device before gluing the screen again.
