---
title: "MacBook Pro A1707 Not turning on, PPBUS G3H shorted to ground repair"
pageid: 192
revid: 594
kind: other
source: "https://repair.wiki/w/MacBook_Pro_A1707_Not_turning_on,_PPBUS_G3H_shorted_to_ground_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1707_Not_turning_on,_PPBUS_G3H_shorted_to_ground_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=594"
last_edited: "2023-10-30T18:53:10Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1707 Not turning on, PPBUS G3H shorted to ground repair

## Problem description
Repair of a common short on PPBUS_G3H on an A1707 MacBook Pro
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- sub 20 ohms on PPBUS_G3H
- Not turning on
## Solution
[How to find short circuits](How_to_find_short_circuits.md)

Inject 1 V (increase if no reaction), watch for hot spots with thermal cam. Usually it's a bad tantalum cap on the PPBUS_G3H rail.

[https://www.youtube.com/watch?v=33M3krGWAOU Example video] (Taking 20 V, 0 A. Ethanol used instead of thermal cam with 0.8 V on PPBUS_G3H, resistance between PPBUS_G3H and CPU coil is 3.6 Ω) Example 2: https://www.youtube.com/watch?v=TZsvvUWUInE (Taking 20 V, 20 mA. Bad capacitor located via visual inspection)

Read the resistance from PPBUS_G3H to Vcore coils (coils around CPU/GPU) IF those measure UNDER 1 Ω (0.3–0.8) then you most likely have a direct 12 V short to CPU/GPU. On this board this situation is always a no fix.
