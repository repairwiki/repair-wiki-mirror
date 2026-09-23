---
title: "MacBook Pro A1502 Battery not recognized repair"
pageid: 472
revid: 1013
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1502_Battery_not_recognized_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1502_Battery_not_recognized_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=1013"
last_edited: "2023-11-08T17:53:42Z"
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
  Type: "Soldering, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1502 Battery not recognized repair

## Problem description
Problem with MacBook Pro A1502 2015-2016 that is not recognizing the battery.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- MacBook not recognizing the battery

## Solution
First, **try a known good battery.**

If it doesn't work, check PPBUS_G3H. If it is 12.23 V, the SMC is not communicating with the battery on its data line, either because the SMC is bad, or because the pullup resistors on the data line are bad. On rare occasion U7100 can pull down the data lines. There is a shared data line between the battery, SMC, and ISL6259 (U7100). If PPBUS_G3H is 12.56 V, then you probably have a bad battery.
