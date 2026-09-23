---
title: "MacBook Pro A1989 No backlight repair"
pageid: 136
revid: 484
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1989_No_backlight_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1989_No_backlight_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=484"
last_edited: "2023-10-29T15:25:44Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1989"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1989"
  Affects_parts: "Motherboard, Display assembly"
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera"
  Type: "Soldering, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1989 No backlight repair

## Problem description
Identifying and solving backlight issues on the A1989 MacBook, as well as similar boards from 2016-2020. A MacBook Pro with no backlight on the display is experiencing an issue where the screen remains dark even though the computer is powered on and operational. This means that while the computer itself may be functioning, the display is not emitting any light, making it extremely difficult or impossible to see the content on the screen. Shining a strong light on the display at an angle might reveal that the content is indeed present, but the backlight is not illuminating it.![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- The display appears completely dark, with no visible content or backlight illumination.
- Occasionally, the backlight might flicker or flash briefly when the MacBook Pro is powered on or waking from sleep, but it remains dark after these brief instances.
- Connecting the MacBook Pro to an external monitor or TV results in a functional display on the external screen, confirming that the computer itself is working correctly.
## Solution
  - Make sure the issue is no backlight, and not no image!**
- Blown backlight fuse rarely if ever happens. This board has a current sensing circuit in place that keeps the backlight fuse from blowing if there is a short to ground on the backlight line.
- Short to ground on backlight output due to bad capacitor on output.
- Bad screen - if backlight voltage is 49-55v, could be bad screen, but not 100% of the time. Could be data communication issues.
- Corrosion on current sense vias/traces for backlight to U8400 LP8548
