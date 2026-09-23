---
title: "MacBook Pro A1706 Not turning on, pulling no current at 5V repair"
pageid: 220
revid: 596
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1706_Not_turning_on,_pulling_no_current_at_5V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1706_Not_turning_on,_pulling_no_current_at_5V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=596"
last_edited: "2023-10-30T18:55:28Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1706"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1706"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1706 Not turning on, pulling no current at 5V repair

## Problem description
MacBook A1706 not powering on, drawing no power and the USB-C charger is stuck at 5V, this is most likely caused by a short on PP3V3_G3H.![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Not turning on
- Not charging
- Zero power draw at 5V as measured by a USB-C meter.
## Solution
PP3V3_G3H is most likely shorted to ground with a 0–1 Ω short, most likely due to bad capacitor. When PP3V3_G3H is directly shorted to ground, it won't produce heat—the PP3V3_G3H power IC is usually smart enough to just turn off when it detects a straight 0 Ω short.

You'll need to identify and replace the shorted component. [How to find short circuits](How_to_find_short_circuits.md)
