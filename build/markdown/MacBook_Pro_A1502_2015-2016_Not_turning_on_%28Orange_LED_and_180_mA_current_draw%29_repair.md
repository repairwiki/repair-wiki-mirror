---
title: "MacBook Pro A1502 2015-2016 Not turning on (Orange LED and 180 mA current draw) repair"
pageid: 479
revid: 1000
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1502_2015-2016_Not_turning_on_(Orange_LED_and_180_mA_current_draw)_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1502_2015-2016_Not_turning_on_(Orange_LED_and_180_mA_current_draw)_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=1000"
last_edited: "2023-11-08T13:12:19Z"
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

# MacBook Pro A1502 2015-2016 Not turning on (Orange LED and 180 mA current draw) repair

## Problem description
180 mA from the charger, the charger light stays orange and machine does not turn on
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Not turning on.
- Only 180 mA current draw from the charge port.

## Solution
Corrosion at U5400 current sensing (R5400) circuit PP3V3_SO_HS_COMPUTING. This device makes power for the stages of CPU_VCORE. U5400 signals the SMC.

- Corrosion for U5400 was removed.
- Jumper wires were added to replace the faulty traces at U5400.
- U5400 and current sense resister restored.
- U7400 (Voltage regulator) chip was replaced and surrounding circuitry restored.
- Backlight circuitry and other areas cleaned up (corrosion).

[https://www.youtube.com/watch?v=l6gqYTJPzbg Example video]
