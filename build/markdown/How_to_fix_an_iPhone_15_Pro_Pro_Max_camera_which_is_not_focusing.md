---
title: "How to fix an iPhone 15 Pro Pro Max camera which is not focusing"
pageid: 6926
revid: 10426
kind: repair_guide
source: "https://repair.wiki/w/How_to_fix_an_iPhone_15_Pro_Pro_Max_camera_which_is_not_focusing"
history: "https://repair.wiki/index.php?title=How_to_fix_an_iPhone_15_Pro_Pro_Max_camera_which_is_not_focusing&action=history"
permalink: "https://repair.wiki/index.php?oldid=10426"
last_edited: "2025-08-20T08:27:55Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 15 Pro"
  - "Repair guides for iPhone 15 Pro Max"
infobox:
  Device: "iPhone 15 Pro, iPhone 15 Pro Max"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering iron, Microscope, Hot Air gun"
  Difficulty: "4. Specialist"
  Type: "Microsoldering"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How to fix an iPhone 15 Pro Pro Max camera which is not focusing

## Problem description
After heavy drop or impact damage, iPhone 15 Pro / Pro Max may boot normally but present issues with camera autofocus and compass.

Even when replacing the rear camera assembly with a known-good unit, the camera fails to focus and the compass does not respond.

In such cases, the root cause is often a damaged **Gyroscope IC** on the logic board.

## Symptoms
![Gyroscope IC location (fig. 1)](images/d/db/Gyroscope-ic-location.png)

- Camera app opens but cannot focus (image stays blurry)
- Compass not working / does not respond to movement
- Replacing camera module does not solve the issue
- Occurs commonly after hard drop or impact damage

## Diagnostic Steps
- Test with a known-good rear camera:

          →If still not focusing, issue is on logic board

- Test Compass / Movement in Compass app:

          → Compass needle does not move

- Inspect logic board under microscope

          → No visible damage to camera PMIC
![Gyroscope IC location on schematic (fig. 2)](images/2/20/Gyroscope-ic-location-schematic.png)

## Repair Steps
- Confirm issue (camera won’t focus + compass not working)
- Replace rear camera with a known-good unit → confirm problem still exists
- Locate Gyroscope IC on the logic board (see fig. 1)
- Carefully remove the damaged Gyroscope IC (Optional: If no iPhone 15 donor is available, harvest a Gyroscope IC from iPhone 14 Pro / Pro Max)
- Clean pads, reball the donor IC
- Install and reflow the donor Gyroscope IC onto the 15 Pro/Max board
- Reassemble the phone and boot
- Test camera focus and compass → both should function normally if replacement was successful
