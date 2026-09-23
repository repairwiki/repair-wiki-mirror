---
title: "MacBook Pro A1990 Not turning on, short on PPBUS G3H repair"
pageid: 113
revid: 501
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1990_Not_turning_on,_short_on_PPBUS_G3H_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1990_Not_turning_on,_short_on_PPBUS_G3H_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=501"
last_edited: "2023-10-29T15:27:03Z"
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

# MacBook Pro A1990 Not turning on, short on PPBUS G3H repair

## Problem description
Repair of a common short on PPBUS_G3H on an A1990 MacBook Pro![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- MacBook not turning on.
- Less than 10 Ohms on PPBUS_G3H as measured with a multimeter (short)
- Very low current draw from the charging port at 5V

## Solution
### Short on PPBUS_G3H
Inject 1V (increase if no reaction), watch for hot spots with thermal cam. Usually it's a bad tantalum cap

Measure PPBUS_G3H to vCORE coils (coils around CPU/GPU) IF those measure UNDER 1Ohm (0.3-0.8) then you most likely have a direct 12V short to CPU/GPU. On this board this situation is always a no fix.
