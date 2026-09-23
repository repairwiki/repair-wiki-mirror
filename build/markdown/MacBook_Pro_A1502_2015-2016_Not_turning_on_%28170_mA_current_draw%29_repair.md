---
title: "MacBook Pro A1502 2015-2016 Not turning on (170 mA current draw) repair"
pageid: 481
revid: 1004
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1502_2015-2016_Not_turning_on_(170_mA_current_draw)_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1502_2015-2016_Not_turning_on_(170_mA_current_draw)_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=1004"
last_edited: "2023-11-08T13:19:18Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1502"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1502"
  Affects_parts: "Whole board"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1502 2015-2016 Not turning on (170 mA current draw) repair

## Problem description
#incomplete
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Not turning on
- Only drawing 170 mA from the magsafe charge port

## Solution
All main rails present except for VCore. Thermal camera showed U8080 getting hot due to short to ground on the output (PP5V_S0_FET). C7740 (1uF 10V) was shorted on the PP5V_S0_BKLT line. Component was corroded due to an insect dying and decomposing on top of that cap. Board was mint otherwise.
