---
title: "MacBook Pro A1708 Not turning on, pulling 0.02A at 20V repair"
pageid: 174
revid: 483
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1708_Not_turning_on,_pulling_0.02A_at_20V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1708_Not_turning_on,_pulling_0.02A_at_20V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=483"
last_edited: "2023-10-29T15:25:41Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1708"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1708"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1708 Not turning on, pulling 0.02A at 20V repair

## Problem description
#incomplete
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Not turning on
- Pulling 20 milliamps at 20V as measured by USB-C meter

## Solution
- Constant low power draw (10–20 mA): Short to ground on power rail (can be PPBUS_G3H, PP3V3_S5, PP3V3_S4,...)

[https://www.youtube.com/watch?v=jYa7KaPkZvg Example video] (19–20 mA draw, 0.7 Ω short to ground on PPBUS_G3H caused by bad capacitor, 1 Ω resistor of current sensing circuit from U7000 (ISL9239) also blown)

- Missing PP3V3_S5G missing due to missing PM_EN_P3V3S5G, caused by bad (solder of) U7800 (PMIC), or corroded capacitors near it

[https://www.youtube.com/watch?v=ssTL3pKda54 Example video]  (Short to ground on PP3V3_S4, PPBUS_G3H 13.7 V, bad capacitor, also damage to USB-C port, replaced CD3215 + other problems) Power cycling 10–30 mA at 20 V: Check for short to ground on PP5V_S4
