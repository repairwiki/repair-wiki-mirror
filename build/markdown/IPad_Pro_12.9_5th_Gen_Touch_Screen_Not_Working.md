---
title: "IPad Pro 12.9 5th Gen Touch Screen Not Working"
pageid: 1226
revid: 12484
kind: repair_guide
source: "https://repair.wiki/w/IPad_Pro_12.9_5th_Gen_Touch_Screen_Not_Working"
history: "https://repair.wiki/index.php?title=IPad_Pro_12.9_5th_Gen_Touch_Screen_Not_Working&action=history"
permalink: "https://repair.wiki/index.php?oldid=12484"
last_edited: "2025-10-31T19:19:41Z"
contributors:
  - "ASRepairs"
  - "VCCBoardRepairs"
  - "KevinShort"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPad Pro 12.9 5th Gen"
  - "Stubs"
infobox:
  Device: "IPad Pro 12.9 5th Gen"
  Affects_parts: "Motherboard"
  Needs_equipment: "Multimeter, Soldering Iron"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPad Pro 12.9 5th Gen Touch Screen Not Working

## Problem description
Fixing a problem where the iPad turns on but the touch screen does not respond to any input.
## Symptoms
- Non working touch
![Fig 1. Check PP15V0_TOUCH_FILT for shorts for No Touch issue](images/4/46/IPad_Pro_12.9_Gen_5_PP15V0_TOUCH_FILT.png)

## Solution
Check for shorts on the capacitors near the two BCM15957A0 touch controllers above the lower display connectors. Often there will be a failed capacitor causing no touch.

Check the following lines for shorts. It could be an IC or a bad capacitor

- PP15V0_TOUCH_FILT (Fig 1)
- PP15V0_TOUCH_LDO (Fig 2)
- PP15V0_TOUCH (Fig 3)

![Fig 2. Check PP15V0_TOUCH_LDO for shorts](images/1/16/IPad_Pro_12.9_Gen_5_PP15V0_TOUCH_LDO.png)
If a capacitor is shorted, you can just remove it & leave it off. The touch issue should be solved

If an IC is shorted, then you'll need to replace it.
![Fig 3. Check PP15V0_TOUCH for shorts](images/1/1a/IPad_Pro_12.9_Gen_5_PP15V0_TOUCH.png)
