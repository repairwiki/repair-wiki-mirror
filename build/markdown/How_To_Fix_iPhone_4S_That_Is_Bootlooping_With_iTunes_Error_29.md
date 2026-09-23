---
title: "How To Fix iPhone 4S That Is Bootlooping With iTunes Error 29"
pageid: 359
revid: 828
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_iPhone_4S_That_Is_Bootlooping_With_iTunes_Error_29"
history: "https://repair.wiki/index.php?title=How_To_Fix_iPhone_4S_That_Is_Bootlooping_With_iTunes_Error_29&action=history"
permalink: "https://repair.wiki/index.php?oldid=828"
last_edited: "2023-11-07T06:35:52Z"
contributors:
  - "VCCBoardRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 4S"
infobox:
  Device: "iPhone 4S"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Insulated Jumper Wire"
  Type: "Soldering"
  Difficulty: "1. Easy"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix iPhone 4S That Is Bootlooping With iTunes Error 29

## Problem description
If the iPhone 4S is Bootloopin and you flash an update  that causes Error 29 (failing at 60% with iTunes flash)

Or 3u Tools Easy Flash failing at 80% (Updating GasGauge).

Then follow these steps to resolve it
![Figure 1. iPhone 4S battery connector area. Shows how R61 is missing due to liquid damage causing the filter to go missing.](images/4/47/IPhone_4s_Missing_R61.png)

## Symptoms
- Bootlooping
- Flashing Apple Logo
- Restarting with the Apple Logo Flashing
- Failing an update with error 29
- Failing at about 60% on iTunes flash
- Failing at 80% on 3u tools with the message "Updating GasGauge"
- ==Solution==
### Diagnostic Steps
- This is often caused by a low-quality replacement battery, use an original battery.
- Check for missing components near the battery connector. See Figure 1.

![Figure 2. Here is a temporary solution on iPhone 4S that had a missing R61 filter. This is for data recovery only.](images/f/f9/IPhone_4S_Jumper_on_R61.png)

### Repair Steps
- A missing R61 resistor near the battery connector can cause this. Replace it.
- For data only, you can also try running a jumper across the pads, to recreate the connection. See Figure 2.
