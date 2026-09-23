---
title: "MacBook Pro A1502 2013-2014 Not turning on (fans full speed) repair"
pageid: 492
revid: 1026
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1502_2013-2014_Not_turning_on_(fans_full_speed)_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1502_2013-2014_Not_turning_on_(fans_full_speed)_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=1026"
last_edited: "2023-11-08T18:04:51Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1502"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1502"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1502 2013-2014 Not turning on (fans full speed) repair

## Problem description
Charger Indicator Shows Green Light, Fan Runs at Full Speed, But the Machine Fails to Power On.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Not turning on
- Green LED on charger is on
- Fans run at full speed

## Solution
Measure voltage on inductor L7310 (CPUVR_PHASE1) located just to the left of the CPU. Should be 1.85–1.95 V

If voltage is missing check for corrosion on other side of the board (in the location where the CPU is positioned but on the back of the board) around C1212. Some capacitors including C1212 could be shorted to ground but that isn't the cause of the fault. Clean up the corrosion first. Check for hot parts using voltage injection and a finger.

In this case it was U8030 TPS22924 3.3 V S0 switch that was shorted and removing the part cleared the short. Replace with good part, problem solved. Example video for this repair: https://www.youtube.com/watch?v=C9Qb32XtROE

Note this repair also applies to the A1502 2015 model but the parts will probably have different U locations.
