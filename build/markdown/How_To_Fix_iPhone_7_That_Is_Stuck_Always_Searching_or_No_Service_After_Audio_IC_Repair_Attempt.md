---
title: "How To Fix iPhone 7 That Is Stuck Always Searching or No Service After Audio IC Repair Attempt"
pageid: 1437
revid: 3135
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_iPhone_7_That_Is_Stuck_Always_Searching_or_No_Service_After_Audio_IC_Repair_Attempt"
history: "https://repair.wiki/index.php?title=How_To_Fix_iPhone_7_That_Is_Stuck_Always_Searching_or_No_Service_After_Audio_IC_Repair_Attempt&action=history"
permalink: "https://repair.wiki/index.php?oldid=3135"
last_edited: "2024-01-22T08:22:19Z"
contributors:
  - "VCCBoardRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone 7"
  - "Repair guides for IPhone 7 Plus"
  - "Stubs"
infobox:
  Device: "IPhone 7, IPhone 7 Plus"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "BGA, Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix iPhone 7 That Is Stuck Always Searching or No Service After Audio IC Repair Attempt

## Problem description
When an iPhone 7 or 7 Plus is Stuck in "Searching" or "No Service" after Audio IC Repair attempt

Baseband Issue after Audio IC![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- After an Audio IC Repair was attempted, you see this:
  - With no SIM Card installed, the phone is always "Searching..." or "No Service".
    - A working phone will show "No SIM" with no SIM Card installed.
  - Dial *#06# in the phone app, and nothing happens
    - A working phone with no Baseband issue, will make the IMEI pop up.
  - If you go to Settings > General > About > Model Firmware is blank

## Solution
When too much heat is used when attempting to remove Audio IC or placing it back, the Baseband CPU (BBCPU) on the opposite end, which is underfilled, will disconnect (or float) and cause these problems

(In addition) if you’re so sure of your skill on audio IC and you get no service after audio IC, before moving to baseband CPU, first try reballing baseband PMU, this is common too.

### Repair Steps
This will require you to reball baseband CPU (BBCPU). This process is a bit risky due to CPU being right next to BBCPU and the potential of floating the main CPU is very high. It is recommended to not risk attempting this repair if you don't have enough experience working with underfilled chips and working next to CPU.

Here's a video of the whole process: https://youtu.be/JP3ghPMjuR0

  - Please note:** If you attempt the above repair, but it's still stuck in "Searching..." or "No Service", then flash an update (**DO NOT RESTORE**). This can sometimes solve the issue. Not sure why it is needed sometimes.

If a phone with a baseband problem is restored, then the iOS software will "erase" the IMEI (baseband info) in the phone and will require the board issue to be fixed, then restored again, so the software will bring back the IMEI.

If you restore, and still has no IMEI, then a baseband/board issue is still present on the board. That will need to be fixed, then restored again.
