---
title: "IPhone 8 Stuck in Searching or No Service Repair"
pageid: 1466
revid: 3203
kind: repair_guide
source: "https://repair.wiki/w/IPhone_8_Stuck_in_Searching_or_No_Service_Repair"
history: "https://repair.wiki/index.php?title=IPhone_8_Stuck_in_Searching_or_No_Service_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3203"
last_edited: "2024-01-24T18:42:48Z"
contributors:
  - "KevinShort"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 8"
  - "Repair guides for iPhone 8 Plus"
  - "Stubs"
infobox:
  Device: "iPhone 8, iPhone 8 Plus"
  Affects_parts: "Motherboard"
  Needs_equipment: "microscope, soldering equipment"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 8 Stuck in Searching or No Service Repair

## Problem description
How to fix an iPhone 8 or iPhone 8 Plus that has no cell service.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
If no previous repairs attempts were made on the phone but these symptoms are present:

- With no SIM Card installed, the phone is always "Searching..." or "No Service".
  - A working phone will show "No SIM" with no SIM Card installed.
- Dial *#06# in the phone app and nothing happens
  - A working phone with no Baseband issue will make the IMEI pop up.
- If you go to Settings > General > About > Model Firmware is blank

## Solution
#### Intel Model
- reballing BBPMU_K should solve it.
  - Part# PMB 6848

#### Qualcomm Model
- Replacing U_PMIC_E (aka BBPMU) should solve it
  - Part# PMD 9655

  - Please note:** If you attempt the above repairs but the phone is still stuck in "Searching..." or "No Service", then flash an update (**DO NOT RESTORE**). This can sometimes solve the issue. Not sure why it is needed sometimes.

If a phone with a baseband problem is restored, then the iOS software will "erase" the IMEI (baseband info) in the phone and will require the board issue to be fixed, then restored again, so the software will bring back the IMEI.

If you restore, and still has no IMEI, then a baseband/board issue is still present on the board. That will need to be fixed, then restored again.  
