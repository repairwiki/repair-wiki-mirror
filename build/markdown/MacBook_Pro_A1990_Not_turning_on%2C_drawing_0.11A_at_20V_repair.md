---
title: "MacBook Pro A1990 Not turning on, drawing 0.11A at 20V repair"
pageid: 124
revid: 500
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1990_Not_turning_on,_drawing_0.11A_at_20V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1990_Not_turning_on,_drawing_0.11A_at_20V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=500"
last_edited: "2023-10-29T15:26:59Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1990"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1990"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1990 Not turning on, drawing 0.11A at 20V repair

## Problem description
A1990 MacBook not turning on and only drawing 0.11A at 20V
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- MacBook not turning on
- current draw of 0.11A at 20V as shown by USB-C meter

## Solution
PP2V5_NAND_SSD0 can be shorted (in this case, PPBUS_G3H luckily didn't go to SSD)

I replaced SSD buck converter but the short was still there, found a shorted cap on the other side of the board C9088 which relieved the short on PP2V5_NAND_SSD0
