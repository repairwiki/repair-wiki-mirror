---
title: "Nintendo Switch Lite No Backlight"
pageid: 7097
revid: 10625
kind: repair_guide
source: "https://repair.wiki/w/Nintendo_Switch_Lite_No_Backlight"
history: "https://repair.wiki/index.php?title=Nintendo_Switch_Lite_No_Backlight&action=history"
permalink: "https://repair.wiki/index.php?oldid=10625"
last_edited: "2025-08-24T14:14:08Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Nintendo Switch Lite"
  - "Stubs"
infobox:
  Device: "Nintendo Switch Lite"
  Affects_parts: "Motherboard"
  Needs_equipment: "Microscope, Soldering iron, multimeter"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Nintendo Switch Lite No Backlight

## Problem description
The device turns on but the image is really hard to see
![Components related to Backlight](images/3/37/Switch_Lite_Backlight_Circuit.jpg)

## Symptoms
- The Backlight is not working

## Solution
This can be caused by a faulty display or a problem in the backlight circuit.

### Diagnostic Steps
The first step is to always try new parts beforte assuming you have motherboard problem so start by testing a new display, Sub Board, Flex that connect the sub-baord to the motherboard.

If parts dont fix the issue the problem is with the backlight circuit.

Start by inspecting the Connector where the flex that comes from the sub-board to the main board for any liquid or physical damage.

If the FPC looks look we need to diagnose the backlight circuit.

The first step is check for shorts in these points, put your multimeter in continuity mode and prove the points in the image bellow these points cant have continuty to ground, if they do there is a short circuit.
![Switch Lite Backlight circuit.png](images/f/fa/Switch_Lite_Backlight_circuit.png)
If there is no shorts next step is check voltages, these voltages ony show up with the device turned on and they display plugged in.

The main voltages we need to check are:

3.6V this the VIN of the backlight Controller

1.8V is the enable signal that comes from the APU, measure this like you need to scrap the point on the board to be able to acess it.

17V is the expected output of a good working backlight circuit,if youhave 17V here the backlight circuit is working and should test parts again.
![Nintendo Switch Backlight Voltages](images/2/2f/Nintendo_Switch_Backlight_Voltages.png)

If 3.6V and 1.8V are ok try and replace the Backlight controller.

## Repair Steps
### Replace the FPC
The FPC is made of plastic so be careful with heat it is easy to melt it when soldering a new one.

This FPC can be found online easily.

### Replacing the Backlight Controller (TPS61163)
Desoldering the Old Chip:

- Cover the FPC with kapton take to avoid melting it.
- Apply heat to the TPS61163 chip from above using a hot air station. Heat for several seconds until the factory solder begins to melt.
- Gently nudge the chip with tweezers. If it moves, it’s ready to be lifted off.
- While the board is still hot, use solder wick and a soldering iron to clean old solder from the motherboard pads.

Soldering the New Chip:

- Align the new chip on the motherboard. Match the dot on the chip to the small triangle marker on the motherboard for correct orientation.
- Heat the chip from above using a hot air station. Watch for the solder to melt, indicated by slight chip movement.
- Gently touch the chip with tweezers to let surface tension settle it into place. Avoid excessive force.

## Final Testing
Turn the console on and make sure the brightness works fine from minimum to maximum
