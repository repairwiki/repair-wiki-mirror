---
title: "IPad Pro 9.7 not displaying any image on the screen repair"
pageid: 1375
revid: 13829
kind: repair_guide
source: "https://repair.wiki/w/IPad_Pro_9.7_not_displaying_any_image_on_the_screen_repair"
history: "https://repair.wiki/index.php?title=IPad_Pro_9.7_not_displaying_any_image_on_the_screen_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=13829"
last_edited: "2026-02-03T06:21:19Z"
contributors:
  - "KevinShort"
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPad Pro 9.7"
  - "Stubs"
infobox:
  Device: "IPad Pro 9.7"
  Affects_parts: "motherboard"
  Needs_equipment: "Multimeter, Soldering Iron"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPad Pro 9.7 not displaying any image on the screen repair

## Problem description
iPad Pro 9.7” powers on and displays an image that is only visible under a flashlight, indicating no backlight. The device otherwise functions normally (touch, sound, boot).

This issue is commonly caused by a blown backlight filter, most frequently FL1728, as well as a smashed FPC connector can cause the backlight filter(s) to blow, so it would require a FPC replacement.

It often occurs when a new display is connected while the battery is still plugged in, causing a current surge that damages the filter.
![iPad Pro 9.7" Backlight Filter Location](images/f/fc/Ipad_pro_9.7_BL_n.png)

## Symptoms
- Screen appears black but image is visible with flashlight
- Device boots normally
- Touch input works
- No backlight brightness at any level
- Issue persists after screen replacement
- No backlight even with known-good display

## Diagnostic Steps
#### 1. Confirm No Backlight
- Shine a flashlight at an angle on the screen
- If image is visible → backlight circuit fault confirmed

----

#### 2. Measure FL1728 (Continuity Mode)
- Locate FL1728 on the logic board
- Set multimeter to continuity
- Probe both sides of the filter

Expected (Good):

- ✅ Continuity present (beep)

Faulty:

- ❌ No continuity → filter is blown/open

## Solution
Replace backlight filter FL1728.

## Repair Steps
1. Disconnect battery
1. Remove logic board from device
1. Locate FL1728 under microscope
1. Apply flux
1. Remove the blown filter using hot air
1. Clean pads carefully
1. Install a known-good replacement filter
1. Inspect solder joints
1. Reassemble device
1. Test backlight functionality
