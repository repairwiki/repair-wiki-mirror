---
title: "GTX 1070 Not turning on (5V short) Repair"
pageid: 1574
revid: 3426
kind: repair_guide
source: "https://repair.wiki/w/GTX_1070_Not_turning_on_(5V_short)_Repair"
history: "https://repair.wiki/index.php?title=GTX_1070_Not_turning_on_(5V_short)_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3426"
last_edited: "2024-02-13T16:10:36Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for GTX 1070"
  - "Repair guides for GTX 1070Ti"
infobox:
  Device: "GTX 1070, GTX 1070Ti"
  Affects_parts: "Whole board"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# GTX 1070 Not turning on (5V short) Repair

## Problem description
Diagnosing and fixing an issue with GTX 1070 that does not turn on and fans don't spin. The issue addressed here related to a short on 5V. If you do not measure less than 50 Ohms on 5V rail, that means this is not your issue!
![5V rail location (Figure 1)](images/6/68/5V_rail_on_Pascal_GPUs.jpg)

## Symptoms
- "Dead" GPU, not turning on
- No picture
- No fan spin
- GPU does not get hot
![Possible shorted components on the 1070 (Figure 2)](images/a/a3/Front_5V_shorts_on_pascal_GPUs.jpg)

## Solution
### Diagnostic Steps
- This issue is characterized by sub 50 Ohms measured on 5V rail on L1 (Figure 1) against ground
- When the short is observed, follow [this guide](Short_Circuits_-_Repair_Basics.md) to locate the shorted component, for 5V rail, this is usually the capacitor next to the inductor L1 or an IC since 5V is used as VCC for those ICs.
  - List of the possible shorted components are on Figure 2.

![Location of the R987 resistor on a reference 1070 (Figure 3)](images/6/6a/R987_pascal.png)

### Repair Steps
- After identifying the shorted component, you will need to de-solder and check whether the short is gone or not
  - If the short is gone, it is recommended to also replace the buck converter as well. Check here for more information [5V Rail on Pascal GPUs Explained](5V_Rail_on_Pascal_GPUs_Explained.md)
  - Sometimes, the input resistor for this converter "R987" (Figure 3) which is a 0 Ohms resistor connecting 12V to the 2nd pin of the buck converter gets blown open because of excess current going through it after the short, if that is the case, you can replace it with another 0 Ohm 0603 SMD resistor or just jump it with a thin wire.
- Assemble the card back and test.
