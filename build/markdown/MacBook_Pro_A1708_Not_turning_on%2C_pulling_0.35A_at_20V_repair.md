---
title: "MacBook Pro A1708 Not turning on, pulling 0.35A at 20V repair"
pageid: 176
revid: 469
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1708_Not_turning_on,_pulling_0.35A_at_20V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1708_Not_turning_on,_pulling_0.35A_at_20V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=469"
last_edited: "2023-10-29T15:21:33Z"
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

# MacBook Pro A1708 Not turning on, pulling 0.35A at 20V repair

## Problem description
#incomplete

Provide a concise description of the issue here. Be  as specific as possible to help readers quickly determine whether or not this is the exact problem they are facing.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Not turning on
- Pulling 350 milliamps at 20V as measured by a USB-C meter

## Solution
PP5V_S5 missing — check and reflow or replace U7650 (TPS51980) with proper pads cleaning (especially on the PPBUS_G3H_P3V3S5 input of U7650). Possible problem: Apple refurbished board; solder over corrosion causing bad joint. [https://www.youtube.com/watch?v=Y0JR1d7AizY Example of replacing a corroded TPS51980]

Dead CPU or bad BIOS can also present like this.
