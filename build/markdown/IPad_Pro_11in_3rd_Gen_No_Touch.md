---
title: "IPad Pro 11in 3rd Gen No Touch"
pageid: 5475
revid: 12041
kind: repair_guide
source: "https://repair.wiki/w/IPad_Pro_11in_3rd_Gen_No_Touch"
history: "https://repair.wiki/index.php?title=IPad_Pro_11in_3rd_Gen_No_Touch&action=history"
permalink: "https://repair.wiki/index.php?oldid=12041"
last_edited: "2025-09-24T00:15:59Z"
contributors:
  - "VCCBoardRepairs"
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPad Pro 11in 3rd Gen"
  - "Stubs"
infobox:
  Device: "IPad Pro 11in 3rd Gen"
  Affects_parts: "Motherboard"
  Needs_equipment: "DCPS, Thermal Camera, Soldering Iron, Hot-Air Station, Microscope"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPad Pro 11in 3rd Gen No Touch

## Problem description
The iPad turns on but touch doesn't work
![iPad Pro 3rd Touch Circuit](images/f/f2/IPad_Pro_3rd_Touch_Circuit.jpg)

## Symptoms
- Touch doesn't work

## Solution
The no touch problem can be caused a faulty screen or a motherboard problem.

### Diagnostic Steps
The first step is to try a new know good screen.

Inspect the 2 touch connectors for any physical damage.

Take diode readings of the FPC and compare them with the 2018 Version the touch circuits are very similiar they even use the same touch ICs.

![iPad Pro 11" 2018 Diode Values to Compare (THX GeekMatics)](images/c/c7/Ipad_pro_3rd_touch_FPC_DIODE_VALUES.png)
Check every filter connected to the touch connectors.

Check for shorts around both Touch ICs(BCM15900B0).

### Repair Steps
If a new screen resolves the no-touch issue, the repair is straightforward and quick

If there is physical damage to the FPC connectors, replace them. The best method is to use a hot air station to desolder the old FPC, clean the old solder from the motherboard, apply new solder, align the new FPC, and use the hot air station to solder it. (Be careful not to use excessive heat, as it may melt the FPC).

When taking diode readings of the FPC, if you measure a line that should read, for example, 0.500V but get 0.100V or 0.000V, it indicates a short on that line. The best way to trace the short is to inject voltage into the line with a DCPS and use a thermal camera to identify which component heats up.

If you measure a line that should read 0.500V but get OL (Open Line), it indicates a disconnection in the circuit. To trace the issue, consult the board view to follow the line’s path.

If a filter connected to the touch connectors is open, replace it with one matching the same specifications or source it from a donor board.

If there is a short on a component near the Touch IC, inject voltage with a DCPS and use a thermal camera to identify which component is heating up.

If none of the above steps resolve the no-touch issue, the next step is to reball or replace both Touch ICs(BCM15900B0) these chips are used in many iPads so they are easy to find.

Sadly there are no schematics available for this model of iPad. if none of the above soluctions fix it there is not much else we can do.

## Final Testing
Assemble the iPad and ensure that the touch functionality works perfectly. The best way to test this is in the Notes app by drawing lines from end to end. Ensure the iPad doesn't exhibit ghost touches.
