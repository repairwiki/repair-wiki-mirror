---
title: "MacBook Pro A1502 2015-2016 Not turning on (90 mA current draw) repair"
pageid: 476
revid: 992
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1502_2015-2016_Not_turning_on_(90_mA_current_draw)_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1502_2015-2016_Not_turning_on_(90_mA_current_draw)_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=992"
last_edited: "2023-11-08T13:05:43Z"
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

# MacBook Pro A1502 2015-2016 Not turning on (90 mA current draw) repair

## Problem description
No power, no green light, 90mA taken, PPBUS_G3H stuck at 12.27 V
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Not turning on
- Only pulling 90 mA from charge port
- No green charge led
- PPBUS_G3H stuck at 12.27 V

## Solution
Corrosion around SMC chip and surrounding components, short on PP3V42_G3H, bad clock chip).

[https://www.youtube.com/watch?v=aMy3xLcH78g Example video]:  (Reflow of SMC, replaced surrounding components, jumper wire, used voltage injection to determine short, replacement of clock chip).
