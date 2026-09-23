---
title: "How To Fix iPhone 8 Stuck In DFU Mode. Error 4014"
pageid: 1526
revid: 3344
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_iPhone_8_Stuck_In_DFU_Mode._Error_4014"
history: "https://repair.wiki/index.php?title=How_To_Fix_iPhone_8_Stuck_In_DFU_Mode._Error_4014&action=history"
permalink: "https://repair.wiki/index.php?oldid=3344"
last_edited: "2024-02-09T08:47:28Z"
contributors:
  - "VCCBoardRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone 8"
  - "Repair guides for IPhone 8 Plus"
  - "Stubs"
infobox:
  Device: "IPhone 8, IPhone 8 Plus"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "BGA, Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix iPhone 8 Stuck In DFU Mode. Error 4014

## Problem description
How To Fix iPhone 8 Stuck In DFU Mode. When you try to update or restore, you will get iTunes Error Code 4014. The screen will stay dark or not lit up.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- You get no image from the screen
- You plug into computer and iTunes/3U tools detects it in DFU mode
- If you try to Update or Restore, you get these results:
  - iTunes Error Code: Error 4014
  - 3u Tools Easy Flash: Fails at 19%

## Solution
### Cause:
- Error 4014 is usually "NAND not detected".

### Solutions:
- Check the caps around NAND to see if they're shorted.
  - If there's a short, remove the shorted cap and try to boot the phone up.
- If no short, pull the NAND and connect it to the JC P13 NAND programmer and see if it's readable
  - You can refer to this video for how to use the P11F Programmer: https://youtu.be/J6n2Bj7sG5A
  - If it doesn't read, the NAND is dead and needs to be replaced
  - If it does read a NAND, then you can reball NAND and install it again. The phone should boot right up.
