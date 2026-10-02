---
title: "MacBook Pro A2251 20V on USB-C, 0.00-0.01A current draw repair"
pageid: 72
revid: 14276
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A2251_20V_on_USB-C,_0.00-0.01A_current_draw_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A2251_20V_on_USB-C,_0.00-0.01A_current_draw_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=14276"
last_edited: "2026-10-02T14:58:18Z"
contributors:
  - "ASRepairs"
  - "JCow"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A2251"
  - "Stubs"
infobox:
  Device: "MacBook Pro A2251"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-10-02"
generated: true
---

# MacBook Pro A2251 20V on USB-C, 0.00-0.01A current draw repair

## Problem description
Dealing with a MacBook (820-01949) showing 20V on USB-C with a current draw of 0.00-0.01A.
![U7800 (Figure 1)](images/b/b5/Microscope_Picture_of_U7800.jpg)
![R8050 (Figure 2)](images/b/b8/Microscope_Picture_of_R8050.jpg)

## Symptoms
- MacBook displaying 20V on USB-C ammeter
- Current draw registering 0.00-0.01A

## Solution
### Diagnostic Steps
#### Check PMU (U7800) Input
- Verify if PMU U7800 (Figure 1) is missing 12V input (PMU_VDD_HI) caused by R8050 (Figure 2) being blown or corroded.
- Check resistance on R8050; normal value should be around **877kΩ**.
- Note: R8050 is part of a voltage divider circuit, so voltage will be lower on pin 2 of the resistor.

### Repair Steps
#### Blown R8050 with Short to Ground
- If R8050 is blown and there's a short to ground on pin 2, replace both U7800 and R8050.

#### Blown R8050 without Short to Ground
- If R8050 is blown but no short to ground is found, replace R8050.
