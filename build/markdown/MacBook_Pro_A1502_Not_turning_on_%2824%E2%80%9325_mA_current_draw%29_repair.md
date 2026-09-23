---
title: "MacBook Pro A1502 Not turning on (24–25 mA current draw) repair"
pageid: 467
revid: 1007
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1502_Not_turning_on_(24%E2%80%9325_mA_current_draw)_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1502_Not_turning_on_(24%E2%80%9325_mA_current_draw)_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=1007"
last_edited: "2023-11-08T17:48:47Z"
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

# MacBook Pro A1502 Not turning on (24–25 mA current draw) repair

## Problem description
#incomplete
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Not turning on.
- Pulling only 24–25 mA from the charge port.

## Solution
- PM_SLP_S4_L missing for random reason, thoroughly inspect clock chip, tiny specks of corrosion next to it can kill it. Sometimes shotgun replacement of the chip is a clean solution.
- [https://www.youtube.com/watch?v=ptG40dIP6rE CHGR_DCIN_D_R shorted to ground].
- Bad right I/O board. Unplug it, see if it works (short on 3.3 V or 5 V rail on the I/O board can cause this problem).
