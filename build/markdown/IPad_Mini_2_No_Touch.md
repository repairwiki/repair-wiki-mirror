---
title: "IPad Mini 2 No Touch"
pageid: 5763
revid: 9094
kind: other
source: "https://repair.wiki/w/IPad_Mini_2_No_Touch"
history: "https://repair.wiki/index.php?title=IPad_Mini_2_No_Touch&action=history"
permalink: "https://repair.wiki/index.php?oldid=9094"
last_edited: "2025-07-27T21:21:04Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPad Mini 2"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPad Mini 2 No Touch

## Problem description
The iPad turns on but touch doesn't work
![iPad Mini 2 Touch Components](images/1/1d/IPad_Mini_2_Touch_Components.png)

## Symptoms
- Touch doesn't work

## Solution
The no touch problem can be caused a faulty digitizer or a motherboard problem.

### Diagnostic Steps
Always try a new digitizer first before assuming you have a motherboard problem.

Inspect the Touch FPC this FPC for any physical damage, it is very easy to damage this FPC by mistake.

![iPad Mini 2 Damaged Touch FPC](images/4/42/IPad_Mini_2_Damaged_Touch_FPC.png)

Take diode readings of the FPC and compare with the image bellow.

![iPad Mini 2 Touch FPC Diode Readings](images/e/ee/IPad_Mini_2_Touch_FPC_Diode_Readings.png)

The next step after cheking diode readings of the FPC is to check if the required voltages are there, these voltages are only present with the device on.

The 2 important voltages need are PP5V25_GRAPE and PP1V8_GRAPE.

## Repair Steps
- If a new digitizer resolves the no-touch issue, the repair is straightforward and quick
- If there is physical damage to the FPC connectors, replace them. The best method is to use a hot air station to desolder the old FPC, clean the old solder from the motherboard, apply new solder, align the new FPC, and use the hot air station to solder it. (Be careful not to use excessive heat, as it may melt the FPC).
- When taking diode readings of the FPC, if you measure a line that should read, for example, 0.500V but get 0.100V or 0.000V, it indicates a short on that line. The best way to trace the short is to inject voltage into the line with a DCPS and use a thermal camera to identify which component heats up.
- If you measure a line that should read 0.500V but get OL (Open Line), it indicates a disconnection in the circuit. To trace the issue, consult the board view to follow the line’s path.
- If a filter connected to the touch connectors is open, replace it with one matching the same specifications (refer to the schematics) or source it from a donor board.
- If PP5V25_GRAPE is missing the problem is with the PMIC (U8100) so replace the PMIC If PP1V8_GRAPE is missing the problem is U1700 so replace U1700
- If none of the above steps resolve the no-touch issue, the next step is to reball the CPU since the touch ic is inside the CPU.

## Final Testing
Assemble the iPad and ensure that the touch functionality works perfectly. The best way to test this is in the Notes app by drawing lines from end to end. Ensure the iPad doesn't exhibit ghost touches.

If you replaced the FPC connector make sure the Home button and case sensor also works.
