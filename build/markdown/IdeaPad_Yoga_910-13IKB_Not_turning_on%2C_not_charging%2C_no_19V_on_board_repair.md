---
title: "IdeaPad Yoga 910-13IKB Not turning on, not charging, no 19V on board repair"
pageid: 1522
revid: 3331
kind: repair_guide
source: "https://repair.wiki/w/IdeaPad_Yoga_910-13IKB_Not_turning_on,_not_charging,_no_19V_on_board_repair"
history: "https://repair.wiki/index.php?title=IdeaPad_Yoga_910-13IKB_Not_turning_on,_not_charging,_no_19V_on_board_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3331"
last_edited: "2024-02-04T14:30:38Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IdeaPad Yoga 910-13IKB"
  - "Stubs"
infobox:
  Device: "IdeaPad Yoga 910-13IKB"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IdeaPad Yoga 910-13IKB Not turning on, not charging, no 19V on board repair

## Problem description
Fixing an issue with the 910-13IKB Lenovo Yoga where it does not turn on nor charge.
![923 7HRZ ISL9237 (Figure 1)](images/3/30/Placeholder_image.jpg)
## Symptoms
- Not turning on
- No 19V on motherboard
- Not charging

## Solution
If charging the battery manually (voltage injection) allows the laptop to power on then the chip on motherboard marked 923 7HRZ (ISL9237) Figure 1 is shorted. This chip monitors system power and talks to the SMBus. Replacing the ISL9237 fixes the problem.
