---
title: "IPhone XR not charging"
pageid: 3835
revid: 6704
kind: repair_guide
source: "https://repair.wiki/w/IPhone_XR_not_charging"
history: "https://repair.wiki/index.php?title=IPhone_XR_not_charging&action=history"
permalink: "https://repair.wiki/index.php?oldid=6704"
last_edited: "2025-05-14T18:36:04Z"
contributors:
  - "Samhext"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone XR"
  - "Stubs"
infobox:
  Device: "IPhone XR"
  Affects_parts: "Motherboard"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone XR not charging

![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Phone does not boot using power button nor plugging in the charger
- Phone charges at 0.013A
- On DC Power Supply, it draws 82mA before prompt to boot

## Solution
- The most likely culprit is Yangtze.
- Replace Yangtze (U3300)
- It is the "Charging IC" for this model
- After replacing, check if the 82mA current draw before prompt to boot is cleared, to confirm the issue is solved.
- In some cases, a liquid damaged ear speaker flex can cause no charging.
  - Try testing with the ear speaker flex unplugged.

Please Note: The shield covering Yangtze is very tough to remove. It is recommended to add 138C low melt solder to all the solder joints around the edges, to make it a little bit easier to remove.

In the process, you may float Baseband or WTR that is under the shield. & cause baseband issues.

Migrated from old wiki
