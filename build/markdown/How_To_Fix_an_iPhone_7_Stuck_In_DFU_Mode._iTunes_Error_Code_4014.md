---
title: "How To Fix an iPhone 7 Stuck In DFU Mode. iTunes Error Code 4014"
pageid: 1472
revid: 3219
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_an_iPhone_7_Stuck_In_DFU_Mode._iTunes_Error_Code_4014"
history: "https://repair.wiki/index.php?title=How_To_Fix_an_iPhone_7_Stuck_In_DFU_Mode._iTunes_Error_Code_4014&action=history"
permalink: "https://repair.wiki/index.php?oldid=3219"
last_edited: "2024-01-25T06:45:35Z"
contributors:
  - "VCCBoardRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone 7 Plus"
  - "Repair guides for iPhone 7"
  - "Stubs"
infobox:
  Device: "iPhone 7, IPhone 7 Plus"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "BGA, Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix an iPhone 7 Stuck In DFU Mode. iTunes Error Code 4014

## Problem description
How to fix an iPhone 7 that is stuck in DFU Mode. When you try to flash an update or restore, it will fail with Error 4014.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- You get no image from the screen
- You plug into computer and iTunes/3U tools detects it in DFU mode
- If you try to Update or Restore, you get these results:
  - iTunes Error Code: Error 401
  - 3u Tools Easy Flash: Fails at 19%

### Solution
Error 4014 is usually "NAND not detected".
- Check the caps around NAND to see if they're shorted.
  - If there's a short, remove the shorted cap and try to boot the phone up.
- If no short, pull the NAND and connect it to the JC P7 NAND programmer and see if it's readable
  - If it doesn't read, the NAND is dead and needs to be replaced
  - If it does read a NAND, then you can reball NAND and install it again. The phone should boot right up.
