---
title: "How To Fix iPhone X With No WiFi. Grayed Out Button"
pageid: 1567
revid: 3408
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_iPhone_X_With_No_WiFi._Grayed_Out_Button"
history: "https://repair.wiki/index.php?title=How_To_Fix_iPhone_X_With_No_WiFi._Grayed_Out_Button&action=history"
permalink: "https://repair.wiki/index.php?oldid=3408"
last_edited: "2024-02-12T07:57:31Z"
contributors:
  - "VCCBoardRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone X"
  - "Stubs"
infobox:
  Device: "IPhone X"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "BGA, Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix iPhone X With No WiFi. Grayed Out Button

## Problem description
How to fix iPhone X with a grayed out WiFi button. This means you cannot enable WiFi, so WiFi functionality will not work
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- WiFi Button is grayed out
- No WiFi

## Solution
In majority of cases, this will be require a bottom board swap.

The bottom layer and interposer break near the SIM tray area.

1. It requires a **bottom board swap**
1. * Check if the board bends near where the SIM slot meets the interposer. Often times you'll see separation in that area.
1. * Split the sandwich, then test the top and bottom boards in the iSocket type of Jig.
1. * If still no WiFi, test the top board with a known good bottom board of the same version (QCOM/Intel) after you unbind WiFi. Doing this will cause baseband not to work, but that's not important right now. We're just testing if WiFi works
1. * If WiFi works with another bottom board, but not the original, then it's related to the bottom board and must be swapped.
1. * There are some chips that are paired on the bottom board and must be swapped over.
1. ** BBCPU (U_MDM_E_)
1. ** Baseband Eeprom (U_EEPROM_E)
1. *** **Be careful**; if you damage or lose this chip, then it's game over. Cellular function will never work.
1. *** A safe way to deal with this, use a eeprom reader, like the JC Module Eeprom reader for the iPhone X.
1. **** While BBCPU is already removed on both original and donor bottom boards, plug in the bottom board to the appropriate slot and read using the JC PC Software. Then remove the bottom board.
1. **** Then plugin the new bottom board and click write.
1. **** Make sure not to mix these up! If you overwrite the original eeprom and lose that data, then it's also gone forever. No way to recover it.
1. ** NFC (NFC_S)
1. *** Although NFC is not required to swap over, it will add extra time to the job if you dont swap it, as you have to go through the "Swipe to recover"/"Attempting data recovery" screen which can take 10–15 min to process.
1. ** Wi-Fi (UWLAN_W)
1. *** Although it's paired, you can unpair it using the iRepair P10 or similar tool that allows you to set the device into Purple Mode and unbind via the lightning port.
1. * Once you swap over all the components above, test again with the iSocket Jig. Make sure all functions work, like:
1. ** You can toggle Wi-Fi on/off
1. ** There is touch
1. ** The phone says "No SIM"
1. *** If it says "Searching" or "No Service" or "Cellular Update Failed", check the sandwich connections again. Make sure there's no dirty flux all over the pads.
1. *** Try reballing BBCPU again, might have been a bad job
1. *** Try reading the original eeprom and writing it the replacement board
1. *** Worst case, try an update on iTunes or 3u tools (flash and retain data), to see if that solves it.
1. **** I don't recommend to restore or you will "lock" yourself out and it will require you to restore each time you "fix" the board issue
