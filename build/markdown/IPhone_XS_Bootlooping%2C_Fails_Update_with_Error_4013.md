---
title: "IPhone XS Bootlooping, Fails Update with Error 4013"
pageid: 4596
revid: 7661
kind: repair_guide
source: "https://repair.wiki/w/IPhone_XS_Bootlooping,_Fails_Update_with_Error_4013"
history: "https://repair.wiki/index.php?title=IPhone_XS_Bootlooping,_Fails_Update_with_Error_4013&action=history"
permalink: "https://repair.wiki/index.php?oldid=7661"
last_edited: "2025-06-14T00:11:44Z"
contributors:
  - "Samhext"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone XS"
  - "Repair guides for IPhone XS Max"
  - "Stubs"
infobox:
  Device: "IPhone XS, IPhone XS Max"
  Affects_parts: "Motherboard, Ear Speaker Flex"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone XS Bootlooping, Fails Update with Error 4013

![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Shows apple logo for about 5 seconds, then blank, then apple logo, then blank
- Sometimes it shows a green flash for a second
- If you try to flash an update or restore, it fails right away with an Error 4013
- If you flash on 3u tools, it fails at 19%

## Solution
#### Flex Cables:
- Step 1 in this case is always unplug all the flex cables.
- Ideally test the board with known good Screen, Battery & Charging Port.
- If it boots, then one of your flexes is the cause.
  - 99% of the time, it is the ear speaker flex. The Flood Illuminator and/or the ALS has liquid damage.
  - The ear speaker flex is paired to the logic board for Face ID.
  - If you want to keep Face ID, you'll need to repair the flex. If Face ID is not important, then you can just replace the flex.
    - To repair the flex, you'll have to desolder the component & clean out all the corrosion, then place them back.
    - If the corrosion is too severe & it damaged the flex, then you'll need to swap the Flood Illuminator and ALS to a new flex, otherwise, you'll lose Face ID.
  - In some cases, another flex can cause this issue like a bad charging port.
    - In this case, just replace the flex

#### Sandwich Issue:
- In some cases, the bootlooping and Error 4013 is caused by liquid damage on the bottom board.
- Underneath the interposer, there are solder balls that connect to the bottom layer.
- This solder is leaded high temp solder, so it's not easy to separate.
- But you can split the top layer & test with a known good bottom board & see if it boots. If so, then your issue is on the bottom board
- Inspect the space between the interposer and bottom layer & check for any signs of corrosion.
- In some cases, you can get away with reflowing the area you find the corrosion.
- The bubbling of the flux can cause enough friction to clear the corrosion causing bridging between pads.
- If this doesn't work, you'll need to do a bottom board swap to get the device working.

Please Note: If the phone is stuck in Recovery Mode because it failed at the Error 4013, you have 2 options

1. Kick the device out of Recovery Mode using 3U Tools. In the main screen of 3U Tools, you'll see a button that says "Exit Recovery Mode"
1. You can attempt another update or restore.

Assuming you fixed the root cause of the bootlooping issue, the above 2 options should get you a working phone.

If it still fails at 4013 or still bootloops, then you haven't solve the issue.

- Migrated from old wiki*
