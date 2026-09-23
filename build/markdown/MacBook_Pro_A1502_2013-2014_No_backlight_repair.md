---
title: "MacBook Pro A1502 2013-2014 No backlight repair"
pageid: 487
revid: 1016
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1502_2013-2014_No_backlight_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1502_2013-2014_No_backlight_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=1016"
last_edited: "2023-11-08T17:55:54Z"
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

# MacBook Pro A1502 2013-2014 No backlight repair

## Problem description
Identifying and solving backlight issues on the A1592 MacBook. A MacBook Pro with no backlight on the display is experiencing an issue where the screen remains dark even though the computer is powered on and operational. This means that while the computer itself may be functioning, the display is not emitting any light, making it extremely difficult or impossible to see the content on the screen. Shining a strong light on the display at an angle might reveal that the content is indeed present, but the backlight is not illuminating it.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- The display appears completely dark, with no visible content or backlight illumination.
- Occasionally, the backlight might flicker or flash briefly when the MacBook Pro is powered on or waking from sleep, but it remains dark after these brief instances.
- Connecting the MacBook Pro to an external monitor or TV results in a functional display on the external screen, confirming that the computer itself is working correctly.
## Solution
  - Make sure the issue is no backlight, and not no image!**

- Blown backlight fuse rarely if ever happens. This board has a current sensing circuit in place that keeps the backlight fuse from blowing if there is a short to ground on the backlight line.
- Short to ground on backlight output (if backlight fuse blown, check this).
- Trace of backlight output interrupted (can be caused by corrosion, can be fixed with jumper wire)

[https://www.youtube.com/watch?v=O0_0YtdwgF0 Example video] (Repaired all corrosion including: LED driver replaced, SMC reflow, Thunderbolt chip replaced, screen connector cleaned and connections resoldered, several corroded components in memory area and screen power area replaced, jumper wire for screen backlight output)

- Bad screen/screen cable. If backlight voltage is 49–50 V, bad screen.
- **USING WRONG SCREEN! If you use a 2012 or a 2015 screen on a 2013–2014 A1502, IT WILL NOT WORK!**

  - If the screen is shorting the backlight to ground,** you can fix the screen if the capacitor/connector on the screen is bad, it just sucks to do. But it is the only option since this screen is no longer available.

  - You can fix the screen if the capacitor/connector on the screen is bad, it just sucks to do. But it is the only option since this screen is no longer available.**
