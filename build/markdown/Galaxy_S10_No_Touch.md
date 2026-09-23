---
title: "Galaxy S10 No Touch"
pageid: 6812
revid: 10238
kind: repair_guide
source: "https://repair.wiki/w/Galaxy_S10_No_Touch"
history: "https://repair.wiki/index.php?title=Galaxy_S10_No_Touch&action=history"
permalink: "https://repair.wiki/index.php?oldid=10238"
last_edited: "2025-08-16T21:52:36Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Galaxy S10"
  - "Stubs"
infobox:
  Device: "Galaxy S10"
  Affects_parts: "Motherboard"
  Needs_equipment: "Soldering Iron, Hot-Air Station, Microscope"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Galaxy S10 No Touch

## Problem description
The device turns on but touch does not work
## Symptoms
- Touch doesnt work.

## Solution
The no touch problem can be caused by a display or a motherboard problem.

### Diagnostic Steps
The first step is to always rule out faulty parts. Start by testing a new display.

If a new display doesnt not solve the issue ispect the Touch and LCD FPC for any physical damage or liquid damage.

Take diode readings of the Touch FPCs and compare them with the image bellow.
![Galaxy S10 SCREEN CONNECTOR - Diode Mode Readings](images/4/46/Galaxy_S10_SCREEN_CONNECTOR_-_Diode_Mode_Readings.jpg)

If everything is ok the next step is to check if the main touch voltages are present.

The main voltages required for this circuit to work are:

- VDD_TSP_1.8V
- VDD_TSP_3.0V

These two voltages can be measured here, keep in mind that these voltages on show up with the device powered on.
![Galaxy S10 Touch Voltages](images/3/30/Galaxy_S10_Touch_Voltages.png)

## Repair Steps
If by replacing by trying a new display the touch fault is solved all you have to do its to replace the display.

If there is a any physical damage to the FPC the solution is to replace it. The best method is to use a hot air station to desolder the old FPC, clean the old solder from the motherboard, apply new solder, align the new FPC, and use the hot air station to solder it. (Be careful not to use excessive heat, as it may melt the FPC).

When taking diode readings of the FPC, if you measure a line that should read, for example, 0.500V but get 0.100V or 0.000V, it indicates a short on that line. The best way to trace the short is to inject voltage into the line with a DCPS and use a thermal camera to identify which component heats up.

If you measure a line that should read 0.500V but get OL (Open Line), it indicates a disconnection in the circuit. To trace the issue, consult the board view to follow the line’s path.

If VDD_TSP_1.8V and VDD_TSP_3.0V  are missing it is probably due to a bad AP PMIC (U12019)  since these lines come from there, replace this chip and see it the problem is solved this component is not underfiled and should be easy to replace, just becareful not to overheat the motherboard because the Storage chip and CPU are on the other side of the PCB.

## Final Testing
After assembling the phone, ensure every function is working as expected, not just the touch circuit.

You can dial *#0*# to enter the test menu.
