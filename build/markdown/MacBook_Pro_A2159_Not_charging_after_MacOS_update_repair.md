---
title: "MacBook Pro A2159 Not charging after MacOS update repair"
pageid: 97
revid: 229
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A2159_Not_charging_after_MacOS_update_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A2159_Not_charging_after_MacOS_update_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=229"
last_edited: "2023-09-28T18:50:20Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A2159"
  - "Stubs"
infobox:
  Device: "MacBook Pro A2159"
  Affects_parts: "Software"
  Needs_equipment: "None"
  Type: "Software"
  Difficulty: "1. Easy"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A2159 Not charging after MacOS update repair

## Problem description
After MacOS upgrade, all 4 USB ports dead. No ability to charge.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Can't charge MacBook

## Solution
Try power button reset. Then try SMC reset. If neither has effect, disconnect battery or discharge battery to 0.

The SMC update during a MacOS upgrade may silently fail leaving no power access to the USB ports. This happened to the author after a Catalina 10.5.7 update. Multiple power button resets and SMC resets may not work. Genius bar is baffled. Disconnecting/discharging the battery to 0 allowed the SMC to fully reset.
