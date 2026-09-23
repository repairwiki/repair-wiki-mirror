---
title: "How To Fix an iPhone 14 that is shows temperature warning and does not charge"
pageid: 7765
revid: 11469
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_an_iPhone_14_that_is_shows_temperature_warning_and_does_not_charge"
history: "https://repair.wiki/index.php?title=How_To_Fix_an_iPhone_14_that_is_shows_temperature_warning_and_does_not_charge&action=history"
permalink: "https://repair.wiki/index.php?oldid=11469"
last_edited: "2025-09-08T22:23:30Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 14"
infobox:
  Device: "iPhone 14"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Microscope, Soldering Iron, Hot Air Station"
  Difficulty: "4. Specialist"
  Type: "Soldering"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix an iPhone 14 that is shows temperature warning and does not charge

## Problem description
iPhone 14 shows temperature warning when powered on. Device charges normally while powered off but does not charge when turned on. Severe overheating occurs once the phone boots.

## Symptoms
- Temperature warning appears after boot.
- Phone charges when powered off, but not when powered on.
- Device overheats rapidly while powered on.
- On DCPS: pre-boot draw ~1A before prompt to boot, then device boots normally.

## Diagnostic Steps
1. Connect to DCPS and observe current draw – confirm abnormal 1A draw before prompt to boot.![Figure 1 - Example of 1A of consumption before prompt to boot](images/6/68/1A-before-boot.png)
1. Check with thermal camera – locate rapid heating component.
1. Identify shorted capacitor on SPKRAMP_TOP_VBOOST line.![Figure 3 - Shorted Capacitor on SPKRAMP_TOP_VBOOST line shown on Boardview](images/c/c3/Shorted_cap_boardview.png)![Figure 2 - Shorted capacitor on SPKRAMP_TOP_VBOOST line](images/b/b0/Shorted_cap.png)
## Repair Steps
1. Remove motherboard from housing, split layer and perform resistance measurement on SPKRAMP_TOP_VBOOST rail.
1. Confirm low resistance indicating short.
1. Identify and remove the shorted capacitor from the rail.
1. Recheck resistance to confirm short is cleared.
1. Reassemble device and test boot with DCPS – ensure pre-boot current draw normalizes.
1. Power on phone and check charging behavior – should now charge normally without temperature warning.
1. Verify device stability under load (charging + usage) before closing repair.![Figure 1 - Example of Temperature warning on iPhone](images/f/fa/Iphone_temp_warning.png)
