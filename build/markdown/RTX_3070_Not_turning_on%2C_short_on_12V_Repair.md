---
title: "RTX 3070 Not turning on, short on 12V Repair"
pageid: 1224
revid: 3430
kind: repair_guide
source: "https://repair.wiki/w/RTX_3070_Not_turning_on,_short_on_12V_Repair"
history: "https://repair.wiki/index.php?title=RTX_3070_Not_turning_on,_short_on_12V_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3430"
last_edited: "2024-02-13T16:57:32Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
infobox:
  Device: "RTX 3070"
  Affects_parts: "PowerStages, Shunt resistors"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# RTX 3070 Not turning on, short on 12V Repair

## Problem description
Fixing an RTX 3070 that showed shorts to ground on 12V from the PCIE lane and one of the 8-pin connectors. The 5V coil also seemed low (~59 ohm).
![RTX 3070, shorted PowerStage (Figure 1)](images/f/f9/RTX_3070,_shorted_mosfet.jpg)

## Symptoms
- Sub 100 Ohms on either 12V from PCIE slot or external 8 pin connector(s)
- Card not turning on or PC shuts off immediately after turning on
- [Shunt resistor(s)](Resistors_-_Repair_Basics.md) likely blown

## Solution
### Diagnostic Steps
- This is HIGHLY likely to be a dead PowerStage/[MOSFET](Transistors_-_Repair_Basics.md).
- To identify which one, see [Short Circuits - Repair Basics](Short_Circuits_-_Repair_Basics.md). You'll need to inject 1V and check for hotspots with either Isopropyl Alcohol or thermal camera.
- Cases like these sometimes have the MOSFET short to OUTPUT instead of GND. This means any voltage injected above 1V might **damage the core.**
  - The best way to safely inject voltage is to connect the negative (-) lead from the LBPSU to the VCore rail, this ensures that VCore will always be at 0V and all the current will return to the PSU before reaching the core.

### Repair Steps
- Replace the identified shorted PowerStage. In this particular case, 2 were shorted, first bottom one for the PCIE slot and 3rd one for 8 Pin connector.
- Check if the short is still present, if not, power up the card and measure all the voltages.
  - If you're missing a voltage rail, this means there is another issue, check the device's page for more guides.
- If everything is okay, assemble the card and stress test.
