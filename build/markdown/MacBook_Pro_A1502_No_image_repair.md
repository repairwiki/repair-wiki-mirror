---
title: "MacBook Pro A1502 No image repair"
pageid: 474
revid: 1017
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1502_No_image_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1502_No_image_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=1017"
last_edited: "2023-11-08T17:57:04Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1502"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1502"
  Affects_parts: "Motherboard, Display assembly"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1502 No image repair

## Problem description
When the MacBook does turn on but there is no image on the LCD. Backlight may be present but the screen is black
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- No image on LCD

## Solution
This problem has multiple causes:

- Bad screen cable
- Screen cable needs reseating (this fixes it a surprising amount of the time)
- Blown L8300
- Bad GPU inside the CPU.
- Bad U8300 causing partial short to ground on 5 V output causing screen to only receive around 3 V. Replace U8300 fixes this issue. Isolate whether the short is on the screen connector side or the U8300 side by removing the nearby inductor and measuring both sides of the pads where the inductor was.

When you find that 5 V is still missing on L8300 and LCD_PWR_EN is missing on U8300, do not chase since 99% of the time this turns out as a no fix (usually bad iGPU or MUX communication issues).
