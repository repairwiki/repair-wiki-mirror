---
title: "MacBook Air A2179 Not turning on, pulling 0 mA at 5V repair"
pageid: 95
revid: 451
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Air_A2179_Not_turning_on,_pulling_0_mA_at_5V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Air_A2179_Not_turning_on,_pulling_0_mA_at_5V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=451"
last_edited: "2023-10-29T15:17:58Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Air A2179"
  - "Stubs"
infobox:
  Device: "MacBook Air A2179"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Air A2179 Not turning on, pulling 0 mA at 5V repair

## Problem description
MacBook not powering up,  SLPS2R and AWAKE voltages/signals all 0, PP3V3_G3H 0.9V, PP3V3_G3H_RTC 3.3V.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- MacBook not powering up.
- SLPS2R and AWAKE voltages/signals all 0.
- PP3V3_G3H 0.9V, PP3V3_G3H_RTC 3.3V.

## Solution
PMU_VDD_HI signal is not reaching U7800 (figure 1) due to corroded R8050 (figure 2).
