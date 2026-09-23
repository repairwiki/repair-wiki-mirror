---
title: "MacBook Pro A1707 Not turning on, pulling 0.22A at 20V repair"
pageid: 206
revid: 572
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1707_Not_turning_on,_pulling_0.22A_at_20V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1707_Not_turning_on,_pulling_0.22A_at_20V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=572"
last_edited: "2023-10-29T16:21:51Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1707"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1707"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1707 Not turning on, pulling 0.22A at 20V repair

## Problem description
#incomplete
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Not turning on
- Drawing 200 mA at 20V as measured by a USB-C meter

## Solution
U8295 getting hot (95 degrees). Short on PP3v3_S0_LEFT, Removed U8295 and injected PP3v3_S0_LEFT, U2800 gets hot. The actual short is on PP3V3_TBT_X_S0 (U2800)
