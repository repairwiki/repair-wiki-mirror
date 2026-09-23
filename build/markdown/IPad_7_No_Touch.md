---
title: "IPad 7 No Touch"
pageid: 4133
revid: 7102
kind: repair_guide
source: "https://repair.wiki/w/IPad_7_No_Touch"
history: "https://repair.wiki/index.php?title=IPad_7_No_Touch&action=history"
permalink: "https://repair.wiki/index.php?oldid=7102"
last_edited: "2025-05-25T21:47:24Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPad 7"
  - "Stubs"
infobox:
  Device: "IPad 7"
  Affects_parts: "Motherboard"
  Needs_equipment: "DCPS, Thermal Camera, Soldering Iron, Hot-Air Station, Microscope"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPad 7 No Touch

## Problem description
The iPad turns but touch doesn't work
![IPad 7 Touch Components](images/2/2d/IPad_7_Touch_Components.png)

## Symptoms
- Touch doesn't work

## Solution
The no touch problem can be caused a faulty digitizer or a motherboard problem.

### Diagnostic Steps
- The first step is to try a new digitizer.
- Inspect the 2 touch connectors for any physical damage.
- Take diode readings of the FPC and compare them with the reference image on this [https://logi.wiki/index.php/iPad_Diode_Mode_Measurements#Digitizer_Connector_1 Page Thanks to Geek Matics]
- Check every filter connected to the touch connectors.
- Check for shorts around the Touch IC.
- Measure the diode reading of the SPI_GRAPE_SCLK line below is an image showing where to measure this line and the expected value.![SPI_GRAPE_SCLK Diode Value](images/d/d1/SPI_GRAPE_SCLK.png)

### Repair Steps
- If a new digitizer resolves the no-touch issue, the repair is straightforward and quick
- If there is physical damage to the FPC connectors, replace them. The best method is to use a hot air station to desolder the old FPC, clean the old solder from the motherboard, apply new solder, align the new FPC, and use the hot air station to solder it. (Be careful not to use excessive heat, as it may melt the FPC).
- When taking diode readings of the FPC, if you measure a line that should read, for example, 0.500V but get 0.100V or 0.000V, it indicates a short on that line. The best way to trace the short is to inject voltage into the line with a DCPS and use a thermal camera to identify which component heats up.
- If you measure a line that should read 0.500V but get OL (Open Line), it indicates a disconnection in the circuit. To trace the issue, consult the board view to follow the line’s path.
- If a filter connected to the touch connectors is open, replace it with one matching the same specifications (refer to the schematics) or source it from a donor board.
- If there is a short on a component near the Touch IC, inject voltage with a DCPS and use a thermal camera to identify which component is heating up.
- If the diode reading of the SPI_GRAPE_SCLK line is low (e.g., near 0V), it indicates a disconnection between the CPU and the motherboard. The only solution is to reball the CPU, a complex repair that should only be performed by an experienced technician.
- If none of the above steps resolve the no-touch issue, the next step is to reball or replace the Touch IC.

## Final Testing
Assemble the iPad and ensure that the touch functionality works perfectly. The best way to test this is in the Notes app by drawing lines from end to end. Ensure the iPad doesn't exhibit ghost touches.
