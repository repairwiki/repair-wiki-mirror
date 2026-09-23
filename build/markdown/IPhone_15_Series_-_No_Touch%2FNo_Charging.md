---
title: "IPhone 15 Series - No Touch/No Charging"
pageid: 6690
revid: 10095
kind: repair_guide
source: "https://repair.wiki/w/IPhone_15_Series_-_No_Touch/No_Charging"
history: "https://repair.wiki/index.php?title=IPhone_15_Series_-_No_Touch/No_Charging&action=history"
permalink: "https://repair.wiki/index.php?oldid=10095"
last_edited: "2025-08-07T19:35:50Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 15"
  - "Repair guides for iPhone 15 Plus"
  - "Repair guides for iPhone 15 Pro"
  - "Repair guides for iPhone 15 Pro Max"
infobox:
  Device: "iPhone 15, iPhone 15 Plus, iPhone 15 Pro, iPhone 15 Pro Max"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Microscope, Hot Air Station, Multimeter, Tweezers, Flux, Soldering tools"
  Difficulty: "3. Hard"
  Type: "Soldering"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 15 Series - No Touch/No Charging

## Problem description
iPhone 15 series devices can suddenly stop charging after being connected to third-party USB-C accessories — especially low-quality or non-Apple cables. This issue typically arises due to damage to the USB-C control circuit, primarily the U9500 IC and its paired EEPROM U9720 chip. These two chips are encrypted and paired, and if either fails or is mismatched, the phone will lose charging and potentially touchscreen functionality as well.

## Symptoms
- iPhone powers on but does not charge
- Touchscreen stops working
- USBC port appears physically fine
![IPHONE 15/15 PLUS USB IC & ROM LOCATION](images/0/0c/IPHONE_15-15_PLUS_USB_IC_&_ROM_LOCATION.png)

## Diagnostic Steps
1. Test with Genuine Cable + Adapter  – Confirm issue persists even with original Apple accessories.
1. Inspect USB-C Port  – Check for corrosion or debris inside port. Clean if necessary.
1. Check for Touch + Charge Combo Fault  – If both touch and charge are not working, suspect U9500 immediately.
1. Open the device and:
1. * Use a thermal camera or rosin + IPA to detect heat/shorts near U9500 area
1. * Visually inspect U9500 and U9720 for damage
1. Board Swap Test  – Install battery, screen, and dock flex on a known good board to rule out flex/battery issues.

## Repair Steps
1. Disassemble the iPhone

- Open the phone, disconnect the battery and remove the logic board.

2.  Locate U9500 & U9720

- The placement of these components varies across iPhone 15 series models. Refer to the board view files or the model-specific diagrams provided in this guide to accurately locate them.
![IPHONE 15 (INTERNATIONAL VARIANT) PRO/PRO MAX USB IC & ROM LOCATION](images/f/fd/IPHONE_15_(INT._VARIANT)_PRO-PRO_MAX_USB_IC_&_ROM_LOCATION.png)
3. Prep the Area

- Apply flux, protect nearby components, and preheat the board if possible.

4. Remove Faulty Chips

- Carefully remove U9500 and U9720 using hot air. Clean pads with wick and flux.

5. Harvest Donor Chips

- From a same-model donor board, remove both U9500 and U9720 (must be a matched pair).

6. Reball & Reinstall

- Reball and Solder U9720 (EEPROM) first, then U9500.

7. Final Inspection

- Clean the area with IPA, inspect for bridges under microscope.

8. Reassemble & Test

- Reconnect everything, power on. Check charging and touch.
![IPHONE 15 (US VARIANT) PRO-PRO MAX USB IC & ROM LOCATION](images/2/2b/IPHONE_15_(US_VARIANT)_PRO-PRO_MAX_USB_IC_&_ROM_LOCATION.png)
