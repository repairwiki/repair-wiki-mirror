---
title: "How To Fix iPhone X That Has No Touch"
pageid: 1566
revid: 3411
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_iPhone_X_That_Has_No_Touch"
history: "https://repair.wiki/index.php?title=How_To_Fix_iPhone_X_That_Has_No_Touch&action=history"
permalink: "https://repair.wiki/index.php?oldid=3411"
last_edited: "2024-02-12T17:57:24Z"
contributors:
  - "ASRepairs"
  - "VCCBoardRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone X"
  - "Stubs"
infobox:
  Device: "IPhone X"
  Affects_parts: "Motherboard, Display assembly"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix iPhone X That Has No Touch

## Problem description
How to fix iPhone X that does not have any touch. New screen will still not touch. Sometimes, this issue is intermittent. Or sometimes it will ghost touch.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- No Touch
- Does not respond to your finger

## Solution
When dealing with an iPhone X with No Touch, first step is to rule out a parts issue:

- Unplug everything, ear speaker flex, power button flex, cameras, antennas, etc.
- Only leave the screen, charging port and battery, then test again
- If still not charging, test with a known good charging port, battery and screen.

  - Please note,** there are 2 version of the iPhone X.

- Qualcomm (CDMA) A1865
- Intel (GSM) A1901, A1902

Troubleshooting and Solutions

Sandwich Separation

1. Most common cause of No Touch is separation between the top layer and interposer. AKA sandwich separation
1. * Diode mode the Touch Connector (J5800)
1. * If you find any lines that are OL, when they should have a Diode Mode reading, high chance the issue is the sandwich separating
1. * Using a preheater/bottom heater, separate the top layer from the interposer
1. * Check for any ripped pads
1. ** If ripped pads, you'll need to repair them by scratching out the vias and traces, which may be difficult in some cases, as the traces are very fragile and small.
1. * Then use an iSocket type of jig, that allows you to connect the top and bottom boards temporarily using spring loaded pins.
1. * If touch works, then reball the sandwich and diode mode the touch connector again.
1. * If the missing Diode Mode readings are back, then it should be solved
1. Sometimes, the damage on the board is not the top layer, but on the bottom layer or bottom board and it requires a **bottom board swap**
1. * Check if the board bends near where the SIM slot meets the interposer. Often times you'll see separation in that area.
1. * Split the sandwich, then test the top and bottom boards in the iSocket type of Jig.
1. * If still no touch, test the top board with a known good bottom board of the same version (QCOM/Intel). Doing this will cause baseband and Wi-Fi not to work, but that's not important right now. We're just testing if touch works
1. * If touch works with another bottom board, but not the original, then it's related to the bottom board and must be swapped.
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
1. **** I don't recommend to restore or you will "lock" yourself out and it will require you to restore each time you "fix" the board issue.
1. If you still have No Touch with known good bottom board, then check this
1. * Check the line PP5V25_TOUCH_VDDH for a short or partial short.
1. * See if the diode mode reading is about 0.643 V
1. * If it's shorted to ground or reading low like 0.235 V, then you have a short.
1. * Pull C5645 and check the diode mode reading again. If it's reading normal at 0.643 V, then replace C5645
1. ** C5645 is 4 μF, 20%, 6.3 V, CER-X5R, 0201

If you did the above but still no touch, try checking all your tools and parts.

Sometimes there's flux that gets the iSocket dirty

Or the extension flex for the iSocket gets damaged leading to no touch

Or maybe your tester screen went bad.
