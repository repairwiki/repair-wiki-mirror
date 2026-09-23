---
title: "MacBook Pro A1706 No backlight repair"
pageid: 225
revid: 607
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1706_No_backlight_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1706_No_backlight_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=607"
last_edited: "2023-10-30T19:08:30Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1706"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1706"
  Affects_parts: "Motherboard, Display assembly"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1706 No backlight repair

## Problem description
Identifying and solving backlight issues on the A1707 MacBook, as well as similar boards from 2016-2020. A MacBook Pro with no backlight on the display is experiencing an issue where the screen remains dark even though the computer is powered on and operational. This means that while the computer itself may be functioning, the display is not emitting any light, making it extremely difficult or impossible to see the content on the screen. Shining a strong light on the display at an angle might reveal that the content is indeed present, but the backlight is not illuminating it.![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- The display appears completely dark, with no visible content or backlight illumination.
- Occasionally, the backlight might flicker or flash briefly when the MacBook Pro is powered on or waking from sleep, but it remains dark after these brief instances.
- Connecting the MacBook Pro to an external monitor or TV results in a functional display on the external screen, confirming that the computer itself is working correctly.
## Solution
  - Make sure the issue is no backlight, and not no image!**
    - Verify that the screen assembly does not have the "flexgate" issue.** Open laptop just a tiny bit and see if image/backlight shows. You can tell it is a flexgate issue when you can see a backlight when the machine is barely open, but you cannot see a backlight once the screen is fully open. This is caused by the screen cable being too short and is a design fault that Apple released a service program for, but only for 13" 2016 models. The exact same cable and therefore the exact same problem also occurs on 15" models but there is no service program for it. To fix the flexgate issue, replace the screen cable with the longer version that is sold as a spare part. [https://www.youtube.com/watch?v=neigIMBUQf0 You can watch a video of how to fix the flexgate issue here....]
- Blown backlight fuse rarely if ever happens. This board has a current sensing circuit in place that keeps the backlight fuse from blowing if there is a short to ground on the backlight line.
- Short to ground on backlight output due to bad capacitor on output.
  - [https://www.youtube.com/watch?v=vOQ0fb9M2m4 Example video] (0 V on backlight circuit, 59 Ω short to ground caused by bad capacitor)

- Bad screen—if backlight voltage is 49–55 V, bad screen. This can also be caused by the flexgate issue. Watch the video linked above for more info on how to fix the flexgate issue.
- Corrosion on current sense vias/traces for backlight to U8400, pins 9 and 10. Example video (skip past TPS51980 replacement): [https://www.youtube.com/watch?v=Y0JR1d7AizY Example video]
