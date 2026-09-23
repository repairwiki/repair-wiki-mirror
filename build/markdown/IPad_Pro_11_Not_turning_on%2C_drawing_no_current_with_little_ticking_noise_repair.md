---
title: "IPad Pro 11 Not turning on, drawing no current with little ticking noise repair"
pageid: 1510
revid: 3311
kind: repair_guide
source: "https://repair.wiki/w/IPad_Pro_11_Not_turning_on,_drawing_no_current_with_little_ticking_noise_repair"
history: "https://repair.wiki/index.php?title=IPad_Pro_11_Not_turning_on,_drawing_no_current_with_little_ticking_noise_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3311"
last_edited: "2024-02-04T14:07:31Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPad Pro 11in 1st Gen"
  - "Stubs"
infobox:
  Device: "IPad Pro 11in 1st Gen"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPad Pro 11 Not turning on, drawing no current with little ticking noise repair

## Problem description
Solving an issue where the iPad 11" 1st gen is not turning on with ticking noise.
![C3800 (Figure 1)](images/3/30/Placeholder_image.jpg)
## Symptoms
- Ticking noise
- Drawing 0A (no current)
- Not turning on

## Solution
This specific problem was traced to a shorted line on PMIC/CD3217. The culprit was a shorted cap C3800 (Figure 1).

It could also be one (or both) the 2 "middle pins connecting from the board to the battery (clk and dat0) that could have been damaged when the battery gets lifted, just make a straight jumper from the motherboard to the battery and that will solve the issue.
