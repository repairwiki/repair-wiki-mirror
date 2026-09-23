---
title: "How to Fix an iPhone 8 Plus boot looping on apple logo and random charging"
pageid: 7703
revid: 11470
kind: repair_guide
source: "https://repair.wiki/w/How_to_Fix_an_iPhone_8_Plus_boot_looping_on_apple_logo_and_random_charging"
history: "https://repair.wiki/index.php?title=How_to_Fix_an_iPhone_8_Plus_boot_looping_on_apple_logo_and_random_charging&action=history"
permalink: "https://repair.wiki/index.php?oldid=11470"
last_edited: "2025-09-08T22:27:19Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 8"
  - "Repair guides for iPhone 8 Plus"
infobox:
  Device: "iPhone 8 Plus, iPhone 8"
  Difficulty: "3. Hard"
  Affects_parts: "Main Logic Board, Front Camera, Charging Port Flex"
  Type: "Soldering, Part Replacement"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How to Fix an iPhone 8 Plus boot looping on apple logo and random charging

## Problem description
Device stuck on Apple logo loop. Boots sometimes but not stable. Charging is inconsistent – sometimes charges, sometimes doesn’t.
![Figure 1 - iPhone 8 / 8 Plus USB (Hydra) IC](images/d/d6/Iphone_8_series_usb_ic.png)

## Symptoms
- Apple logo loop, device fails to boot reliably.
- Random charging behavior.
- New battery tested, no change.
- On DCPS: current draw jumps directly to 0.200A when prompting to boot.
- Not charging consistently even with known good cables.
- Hydra IC shows heating on thermal inspection.
![Figure 2 - iPhone 8 / 8 Plus Front Camera](images/7/73/Iphone_8_series_front_camera.png)

## Diagnostic Steps
1. Visual Inspection
1. * Check for corrosion or damage around Hydra IC, Tristar, and battery connector.
1. DCPS Analysis
1. * Normal preboot sequence should ramp (0.020A → 0.080A → 0.200A).
1. * Direct jump to 0.200A suggests fault in Hydra/Tristar/PMIC path.
1. Parts Swapping
1. * Battery replaced → no effect.
1. * Test with known good charging port flex.
1. * Test with known good Front facing camera.
1. Thermal Check
1. * Hydra IC heating indicates abnormal activity.
![Figure 3 - iPhone 8 / 8 Plus Charge Port](images/4/48/8PlusChargePort.png)

## Repair Steps
1. Replace/test charging port flex.
1. Replace/test Front facing camera.
1. If issue persists → replace Hydra IC.
1. Test device boot and charging behavior on DCPS (expect proper ramping).
1. Confirm final: stable boot, consistent charging, normal thermal profile.
