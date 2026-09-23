---
title: "IPhone XR is bootlooping and fails itunes update with error 4013"
pageid: 3837
revid: 6708
kind: repair_guide
source: "https://repair.wiki/w/IPhone_XR_is_bootlooping_and_fails_itunes_update_with_error_4013"
history: "https://repair.wiki/index.php?title=IPhone_XR_is_bootlooping_and_fails_itunes_update_with_error_4013&action=history"
permalink: "https://repair.wiki/index.php?oldid=6708"
last_edited: "2025-05-14T18:48:26Z"
contributors:
  - "Samhext"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone XR"
  - "Stubs"
infobox:
  Device: "IPhone XR"
  Affects_parts: "Flex cables"
  Type: "Soldering, Part replacement"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone XR is bootlooping and fails itunes update with error 4013

![iPhone FaceID sensors and locations](images/b/b7/Image-1758.png)
[^1]

## Symptoms
- Shows apple logo for about 5 seconds, then blank, then apple logo, then blank
- Sometimes it shows a green flash for a second
- If you try to flash an update or restore, it fails right away with an Error 4013
- If you flash on 3u tools, it fails at 19%

## Solution
Flex cables:

- Step 1 in this case is always unplug all the flex cables.
- Ideally test the board with known good Screen, Battery & Charging Port.
- If it boots, then one of your flexes is the cause.
  - 99% of the time, it is the ear speaker flex. The Flood Illuminator and/or the ALS has liquid damage.
  - The ear speaker flex is paired to the logic board for Face ID.
  - If you want to keep Face ID, you'll need to repair the flex. If Face ID is not important, then you can just replace the flex.
    - To repair the flex, you'll have to desolder the Flood illuminator  & clean out all the corrosion, then place them back.
    - If the corrosion is too severe & it damaged the flex, then you'll need to swap the Flood Illuminator and ALS to a new flex, otherwise, you'll lose Face ID.
  - In some cases, another flex can cause this issue like a bad charging port.
    - In this case, just replace the flex

Please Note: If the phone is stuck in Recovery Mode because it failed at the Error 4013, you have 2 options

1. Kick the device out of Recovery Mode using 3U Tools. In the main screen of 3U Tools, you'll see a button that says "Exit Recovery Mode"
1. You can attempt another update or restore.

Assuming you fixed the root cause of the bootlooping issue, the above 2 options should get you a working phone.

If it still fails at 4013 or still bootloops, then you haven't solve the issue.

Migrated from old wiki

[^1]: https://www.simplymac.com/iphone/iphone-dot-projector-explained
