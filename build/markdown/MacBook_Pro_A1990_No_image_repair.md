---
title: "MacBook Pro A1990 No image repair"
pageid: 119
revid: 498
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1990_No_image_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1990_No_image_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=498"
last_edited: "2023-10-29T15:26:52Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1990"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1990"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1990 No image repair

## Problem description
When the MacBook does turn on but there is no image on the LCD. Backlight may be present but the screen is black
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- No image on LCD

## Solution
- Check the LCD cable and the connector on both the screen side and the logic board side.
  - The backlight power line is right next to the eDP data line for the image.
  - Any minor corrosion here results in 30 volts or more going to the displayport mux, U9850.
    - U9850 is what the dedicated GPU and the CPU's integrated GPU go to before it goes to the screen.
    - Unlike the 13" machine where the backlight voltage destroys the CPU, here it destroys a cheap chip.
      - Replace U9850, and the screen cable, and the connector(on the screen side and the logic board side) and it will usually be fine.
