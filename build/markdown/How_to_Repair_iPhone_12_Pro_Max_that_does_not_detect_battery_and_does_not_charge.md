---
title: "How to Repair iPhone 12 Pro Max that does not detect battery and does not charge"
pageid: 8265
revid: 12106
kind: repair_guide
source: "https://repair.wiki/w/How_to_Repair_iPhone_12_Pro_Max_that_does_not_detect_battery_and_does_not_charge"
history: "https://repair.wiki/index.php?title=How_to_Repair_iPhone_12_Pro_Max_that_does_not_detect_battery_and_does_not_charge&action=history"
permalink: "https://repair.wiki/index.php?oldid=12106"
last_edited: "2025-09-26T02:35:04Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 12 Pro Max"
infobox:
  Device: "iPhone 12 Pro Max"
  Needs_equipment: "Soldering Iron, Hot Air Station, Tweezer, Flux"
  Affects_parts: "Main Logic Board"
  Difficulty: "4. Specialist"
  Type: "Soldering"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How to Repair iPhone 12 Pro Max that does not detect battery and does not charge

## Problem Description
An iPhone 12 Pro Max shows no charging and battery not detected, even after replacing the charging port, using a new cable and charging cable/brick.

- Battery connector voltage (BATT_VCC) reads 3.7–4.0 V (normal).
- Charging IC and USB IC measure fine.
- Battery FPC diode readings normal.

Root cause: low I²C voltage (0.2V instead of 1.8V) on SDA/SCL pins.

Tracing these lines leads to U2470, the battery data level translator IC.

Replacing U2470 restores I²C communication, allowing the phone to detect the battery and charge normally.
----
![iPhone 12 Pro Max - Battery Pins](images/d/da/12pm-u2470-batt-pins.png)

## Symptoms
- iPhone does not charge or power from the battery.
- Battery percentage not displayed, device may only run on DCPS.
- No corrosion or damage visible on battery connector area.

----
![iPhone 12 Pro Max U2470 - Schematic](images/e/e7/12pm-u2470-schematics.png)

## Diagnostic Steps
1. Measure Battery Connector Voltage
1. * BATT_VCC → 3.7–4.0V = ✅ Good
1. * If missing, diagnose power path first.
1. Check Battery FPC Diode Mode
1. * All lines read within normal range = ✅
1. Measure I²C Lines (SCL/SDA)
1. * Expected: ~1.8 V
1. * Observed: ~0.2 V → indicates line is being pulled low.
1. Trace I²C Lines to U2470
1. * Locate U2470 (near battery FPC).
1. * Check for damage/corrosion.
1. * If clean, suspect internal short or failure pulling bus low.

----
![iPhone 12 Pro Max - U2470 Location](images/e/e9/12pm-u2470.png)

## Repair Steps
### 1. Remove Faulty U2470
- Use hot air station to remove U2470.
- Clean pads, inspect for shorts.

### 2. Replace U2470
- Install a new/reballed U2470.
- Align carefully.

### 3. Verify Voltages
- After installation, re-check I²C voltage at battery FPC:
  - Should now be ~1.8V.

### 4. Final Test
- Connect battery, boot phone.
- Confirm battery is detected, percentage shows, and device charges.
