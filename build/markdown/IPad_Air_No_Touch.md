---
title: "IPad Air No Touch"
pageid: 5781
revid: 9101
kind: other
source: "https://repair.wiki/w/IPad_Air_No_Touch"
history: "https://repair.wiki/index.php?title=IPad_Air_No_Touch&action=history"
permalink: "https://repair.wiki/index.php?oldid=9101"
last_edited: "2025-07-27T21:57:39Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPad Air"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPad Air No Touch

## Problem description
The iPad turns on but touch doesn't work
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Touch doesnt work

## Solution
The no touch problem can be caused by a faulty digitizer or a motherboard problem.

### Diagnostic Steps
Start by testing a new digitizer before assuming you have a motherboard problem.

Inspect the 2 Touch FPCs for any physical damage.

Take diode readings of the Touch FPCs and compare them with the image bellow.
![J6620 Diode Readings](images/8/83/J6620_Diode_Readings.png)

![J6640 Diode Readings](images/8/85/J6640_Diode_Readings.png)

If everything is ok the next step is to check if the touch ICs(Cumulus) have the required voltages to work.

The main voltages required for this circuit to work are:

- PP5V25_GRAPE
- PP1V8_GRAPE_SW

These voltages can be measured here :
![iPad Air 1 Touch Voltages](images/e/e8/IPad_Air_1_Touch_Voltages.png)

### Repair Steps
If by replacing by trying a new digitizer the touch fault is solved all you have to do its to replace the digitizer.

If there is a any physical damage any of the FPCs the solution is to replace the damaged one. The best method is to use a hot air station to desolder the old FPC, clean the old solder from the motherboard, apply new solder, align the new FPC, and use the hot air station to solder it. (Be careful not to use excessive heat, as it may melt the FPC).

When taking diode readings of the FPC, if you measure a line that should read, for example, 0.500V but get 0.100V or 0.000V, it indicates a short on that line. The best way to trace the short is to inject voltage into the line with a DCPS and use a thermal camera to identify which component heats up.

If you measure a line that should read 0.500V but get OL (Open Line), it indicates a disconnection in the circuit. To trace the issue, consult the board view to follow the line’s path.

If PP5V25_GRAPE it is probably due to a bad PMIC(8100) since this line comes from there, this chip is glued to the PCB with underfill and it not recomend to replace without practice.

If PP1V8_GRAPE_SW it is probably due to a bad U6500 since this line comes from there.
![iPad Air 1 U6500](images/c/c9/U6500_iPad_Air_1.png)

If the required voltages are present and the diode readings are ok the next step is to replace both Cumulus ICs these chips is present on many devices like the 6 and 6 Plus, iPad Mini 1, iPad Mini 2, iPad Mini 3, iPad Mini 4 and iPad 5, so if you have any of these devices you harvest from a donor board, or you can buy the chip new online its very easy to find the reference is **BCM5976.**

To replace the your hot air station to desolder them, then add low melt solder to the pads on the motherboard after that clean the solder leaving a flat surface to solder the new chip. Be careful with heat since the the Touch FPCs are near by, i recommend covering them with kapton tape.

## Final Testing
Assemble the iPad and ensure that the touch functionality works perfectly. The best way to test this is in the Notes app by drawing lines from end to end.
