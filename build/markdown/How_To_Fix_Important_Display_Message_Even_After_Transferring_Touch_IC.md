---
title: "How To Fix Important Display Message Even After Transferring Touch IC"
pageid: 8175
revid: 11976
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_Important_Display_Message_Even_After_Transferring_Touch_IC"
history: "https://repair.wiki/index.php?title=How_To_Fix_Important_Display_Message_Even_After_Transferring_Touch_IC&action=history"
permalink: "https://repair.wiki/index.php?oldid=11976"
last_edited: "2025-09-21T11:09:40Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 12"
  - "Repair guides for iPhone 12 Mini"
  - "Repair guides for iPhone 12 Pro"
  - "Repair guides for iPhone 12 Pro Max"
  - "Repair guides for iPhone 13"
  - "Repair guides for iPhone 13 Mini"
  - "Repair guides for iPhone 13 Pro"
  - "Repair guides for iPhone 13 Pro Max"
  - "Repair guides for iPhone 14"
  - "Repair guides for iPhone 14 Plus"
  - "Repair guides for iPhone 14 Pro"
  - "Repair guides for iPhone 14 Pro Max"
  - "Repair guides for iPhone 15"
  - "Repair guides for iPhone 15 Plus"
  - "Repair guides for iPhone 15 Pro"
  - "Repair guides for iPhone 15 Pro Max"
  - "Repair guides for iPhone 16"
  - "Repair guides for iPhone 16 Pro"
  - "Repair guides for iPhone 16 Pro Max"
  - "Repair guides for iPhone 16e"
infobox:
  Device: "iPhone 12, iPhone 12 Pro, iPhone 12 Mini, iPhone 12 Pro Max, iPhone 13, iPhone 13 Pro, iPhone 13 Mini, iPhone 13 Pro Max, iPhone 14, iPhone 14 Pro, iPhone 14 Plus, iPhone 14 Pro Max, iPhone 15, iPhone 15 Pro, iPhone 15 Plus, iPhone 15 Pro Max, iPhone 16, iPhone 16 Pro, iPhone 16e, iPhone 16 Pro Max"
  Affects_parts: "Display"
  Needs_equipment: "JC Programmer"
  Difficulty: "3. Hard"
  Type: "Programming"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix Important Display Message Even After Transferring Touch IC

## Problem Description
When performing a display replacement on iPhone models that require Touch IC transfer (e.g. iPhone 12-16 series), even after transferring the original touch IC from the old display to the new one, the “Unable to verify this iPhone has a genuine Apple display” message still shows up.

This usually occurs due to MTSN data mismatch — the new display doesn’t have the correct pairing data that tells the phone it’s the original display.
----

## Symptoms
- “Important Display Message” still shows after successful touch IC transfer.
- Everything else (touch, brightness, Face ID) may work fine.!["Important Display Message"](images/2/21/Display-message.png)

----

## Diagnostic Steps
1. Confirm touch IC transfer was done properly (no bad solder joints, no missing pads).
1. Connect phone to JC Programmer or equivalent tool and check if MTSN data on new display matches old display.
1. If mismatch is found, message will continue to display until data is written correctly.

----

## Repair Steps
### Method 1: Pre-Transfer MTSN Data
1. Read Old Display MTSN Data:
1. * Before transferring touch IC, connect old display to JC V1SE/V1SPRO  programmer.![Connect Display to Appropriate Connector](images/a/ab/CONNCET-DISPLAY.png)
1. * Select Read MTSN or Read Display Data and save to PC/programmer.![Read](images/6/6a/READ.png)
1. Write to New Display:
1. * Connect new display to programmer.
1. * Select Write MTSN or Write Display Data to program old display’s data to the new one. ![WRITE](images/b/bd/WRITE.png)
1. Transfer Touch IC:
1. * Once data is written, perform touch IC transfer normally.
1. * Install new display → message should be gone.

----

### Method 2: Post-Transfer Fix (If Already Transferred Touch IC)
1. Connect Phone to Programmer:
1. * After touch IC transfer, connect phone with new display installed to JC Programmer.
1. Use Fix True Tone Option:
1. * On JC Programmer, select Fix True Tone.![TP Fix](images/5/57/TP-FIX.png)
1. * Select the appropriate display you are using, original or third party.![Select Display](images/e/e6/SELECT-DISPLAY.png)
1. * This will rewrite correct MTSN data to the new display flex.![Verified correct data written to new display](images/8/87/WRITE-COMPLETED.png)
1. Reboot Phone:
1. * Power cycle device → confirm that “Important Display Message” is cleared.
