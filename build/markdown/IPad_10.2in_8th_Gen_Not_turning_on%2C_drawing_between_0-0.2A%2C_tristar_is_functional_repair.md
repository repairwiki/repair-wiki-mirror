---
title: "IPad 10.2in 8th Gen Not turning on, drawing between 0-0.2A, tristar is functional repair"
pageid: 1513
revid: 5228
kind: repair_guide
source: "https://repair.wiki/w/IPad_10.2in_8th_Gen_Not_turning_on,_drawing_between_0-0.2A,_tristar_is_functional_repair"
history: "https://repair.wiki/index.php?title=IPad_10.2in_8th_Gen_Not_turning_on,_drawing_between_0-0.2A,_tristar_is_functional_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=5228"
last_edited: "2024-11-08T06:17:48Z"
contributors:
  - "ASRepairs"
  - "VCCBoardRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPad 8"
  - "Stubs"
infobox:
  Device: "IPad 8"
  Affects_parts: "Main Logic Board, PMIC"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPad 10.2in 8th Gen Not turning on, drawing between 0-0.2A, tristar is functional repair

## Problem description
Solving an issue where the iPad 10.2in 8th gen would not turn on, cycles power draw from 0A to 0.300A then the screen would flash and cycle again and the Tristar is working as intended.
![PMIC on the board (Figure 1)](images/3/30/Placeholder_image.jpg)
## Symptoms
- Flashing screen
- Cycling power draw (0-0.3A)

## Solution
This specific problem was caused by bad PMIC failing to output GPIO_PMU_TO_LCD_PWREN.

Replacing PMIC solved the issue.
