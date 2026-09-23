---
title: "IPhone 12 Stuck on the Apple Logo Error 4013 Repair"
pageid: 1406
revid: 3072
kind: repair_guide
source: "https://repair.wiki/w/IPhone_12_Stuck_on_the_Apple_Logo_Error_4013_Repair"
history: "https://repair.wiki/index.php?title=IPhone_12_Stuck_on_the_Apple_Logo_Error_4013_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3072"
last_edited: "2024-01-19T22:23:02Z"
contributors:
  - "KevinShort"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone 12"
  - "Repair guides for IPhone 12 Mini"
  - "Repair guides for IPhone 12 Pro"
  - "Repair guides for IPhone 12 Pro Max"
  - "Stubs"
infobox:
  Device: "IPhone 12, IPhone 12 Pro, IPhone 12 Pro Max, IPhone 12 Mini"
  Affects_parts: "Motherboard"
  Needs_equipment: "screwdrivers, spudger"
  Type: "Part replacement"
  Difficulty: "1. Easy"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 12 Stuck on the Apple Logo Error 4013 Repair

## Problem description
Diagnosis and repair of an iPhone 12 that boot loops and only shows the Apple logo on screen.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Shows Apple logo for about 5 seconds, then blank, then Apple logo, then blank.
- Sometimes it shows a green flash for a second.
- If you try to flash an update or restore, it fails right away with an Error 4013.
- If you flash on 3U Tools, it fails at 19%.

## Solution
Flex Cables:

- Step 1 in this case is always unplug all the flex cables.
- Ideally test the board with known good screen, battery & charging port.
- If it boots, then one of your flexes is the cause.
  - 99% of the time, it is the ear speaker flex. The flood illuminator and/or the ALS has liquid damage.
  - The ear speaker flex is paired to the logic board for Face ID.
  - If you want to keep Face ID, you'll need to repair the flex. If Face ID is not important, then you can just replace the flex.
    - To repair the flex, you'll have to desolder the component & clean out all the corrosion, then place them back.
    - If the corrosion is too severe & it damaged the flex, then you'll need to swap the flood illuminator and ALS to a new flex, otherwise, you'll lose Face ID.
  - In some cases, another flex can cause this issue like a bad charging port.
    - In this case, just replace the flex

Please Note: If the phone is stuck in Recovery Mode because it failed at the Error 4013, you have 2 options

1. Kick the device out of Recovery Mode using 3U Tools. In the main screen of 3U Tools, you'll see a button that says "Exit Recovery Mode"
1. You can attempt another update or restore.
