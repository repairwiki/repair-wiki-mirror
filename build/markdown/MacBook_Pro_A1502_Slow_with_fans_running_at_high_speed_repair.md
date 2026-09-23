---
title: "MacBook Pro A1502 Slow with fans running at high speed repair"
pageid: 475
revid: 1019
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1502_Slow_with_fans_running_at_high_speed_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1502_Slow_with_fans_running_at_high_speed_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=1019"
last_edited: "2023-11-08T17:57:49Z"
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

# MacBook Pro A1502 Slow with fans running at high speed repair

## Problem description
The machine running exceptionally slow with the fans spinning fast denotes a sensor issue. When a sensor is off, and it thinks the voltage/current is too high/low somewhere, or that the temperature is too high/low somewhere, it will clock the machine down and cause the fan to run at max speed. You have to use a tool that reads sensors like hwsensors, or boot into a Linux distribution to check your sensors, then chase down the circuit responsible for that sensor using the schematic/boardview. If all sensors are off, this usually points to an issue with the SMC or PP3V3_S5_AVREF_SMC.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- MacBook running abnormally slow.
- Fans spinning very fast.

## Solution
- Bad trackpad can cause sensor issue. Water gets to the trackpad first in many occasions.
- Q5871 corroded, difficult to see without microscope, on edge of board.
- U5870 corroded, on edge of board next to fan where water comes in.
