---
title: "IPhone 11 No Cellular Service, No IMEI Present"
pageid: 4600
revid: 7670
kind: repair_guide
source: "https://repair.wiki/w/IPhone_11_No_Cellular_Service,_No_IMEI_Present"
history: "https://repair.wiki/index.php?title=IPhone_11_No_Cellular_Service,_No_IMEI_Present&action=history"
permalink: "https://repair.wiki/index.php?oldid=7670"
last_edited: "2025-06-14T00:41:23Z"
contributors:
  - "Samhext"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone 11"
  - "Stubs"
infobox:
  Device: "IPhone 11"
  Affects_parts: "Motherboard"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 11 No Cellular Service, No IMEI Present

![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
Here are the symptoms for cellular signal issues

- With no SIM Card installed, the phone is always "Searching..." or "No Service".
  - A working phone will show "No SIM" with no SIM Card installed.
- Dial *#06# in the phone app, and nothing happens
  - A working phone with no Baseband issue, will make the IMEI pop up.
- If you go to Settings > General > About > Model Firmware is blank

## Solution
#### Sandwich separation
- Split the sandwich & check for ripped pads on the top layer
  - If so, try to fix the ripped pads by scratching out the vias/traces & rebuild the pads using solder lugs
- If no obvious bends, then test the 2 layers with the iSocket type of jig. This allows you to connect the 2 layers without soldering, for testing purposes.
- See if the above symptoms are resolved. If so, sandwich the 2 layers back together & fully test with an active SIM & make sure all functions work
  - Including making a phone call & checking for sound through phone call
  - No sound during a phone call points towards a bad sandwich reball or separation

#### Cracked "WTR"
- WTR is the transceiver chip, labeled "U_XCVR" on this model
- It is often cracked, so visually check it for any cracks on the physical chip.
- Part# on the chip itself: 5765
- If the chip is cracked, replace it, re-sandwich the board & test again.

#### Bottom Board Swap
- Doing a bottom board swap is an easy way to rule out the whole cellular circuit, as it's pretty much all located on the bottom board.
- You do need to transfer the BBCPU, BB Eeprom & WiFi.
- You should consider swapping over NFC as well, although it's not required.

#### BBCPU Reball
- You can considering trying a BBCPU reball to see if this fixes the baseband issue
- This is good for someone who doesn't have a replacement bottom board available.
- Although there's a lower chance of success, as baseband issues aren't always a BBCPU reball solution.
  - It could be BBPMU
  - Or some other part of the complex circuit.

#### PA_HB_K shorted
- replace amplify radio signal strength

  - Please note:** If you attempt the above repairs, but it's still stuck in "Searching..." or "No Service", then flash an update (**DO NOT RESTORE**). This can sometimes solve the issue. Not sure why it is needed sometimes.

If a phone with a baseband problem is restored, then the iOS software will "erase" the IMEI (baseband info) in the phone and will require the board issue to be fixed, then restored again, so the software will bring back the IMEI.

If you restore, and still has no IMEI, then a baseband/board issue is still present on the board. That will need to be fixed, then restored again.

- Migrated from old wiki*
