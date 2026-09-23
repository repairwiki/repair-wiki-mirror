---
title: "MacBook Air A2179 Not turning on, pulling ~180-220 mA then going down to 20 mA at 5V repair"
pageid: 94
revid: 456
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Air_A2179_Not_turning_on,_pulling_~180-220_mA_then_going_down_to_20_mA_at_5V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Air_A2179_Not_turning_on,_pulling_~180-220_mA_then_going_down_to_20_mA_at_5V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=456"
last_edited: "2023-10-29T15:19:01Z"
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

# MacBook Air A2179 Not turning on, pulling ~180-220 mA then going down to 20 mA at 5V repair

## Problem description
MacBook not turning on, 180-220 mA usage before going down to 20 milliamps, P5VG3S_EN missing. All rails below PP5V_G3S are present.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- MacBook not powering up.
- Drawing 180-220 mA then going down to 20 mA at 5V as measured by a USBC meter.
- P5VG3S_EN missing.
- All rails below PP5V_G3S are present.

## Solution
The PMIC is dead, U7800 (Figure 1). Replace it.
