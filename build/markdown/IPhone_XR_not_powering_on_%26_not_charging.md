---
title: "IPhone XR not powering on & not charging"
pageid: 3737
revid: 6566
kind: repair_guide
source: "https://repair.wiki/w/IPhone_XR_not_powering_on_%26_not_charging"
history: "https://repair.wiki/index.php?title=IPhone_XR_not_powering_on_%26_not_charging&action=history"
permalink: "https://repair.wiki/index.php?oldid=6566"
last_edited: "2025-05-13T08:06:12Z"
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
  Type: "Soldering, BGA"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone XR not powering on & not charging

![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Not powering on
- Not Charging
- Low amperage draw from DCPSU
- No short to ground on VDD Main, VDD Boost, or PP3V0_NAND

## Solution
The charging IC that fails most commonly on this model is the Yangtze IC (U3300). This was the Tigris IC in previous models. It is under the bottom back shield. Use max heat, max air, largest nozzle to remove shield. It requires a lot of heat or tin snips to cut the shield. Be EXTREMELY careful not to float anything or knock off components. Be careful with how much force you use as too much force can flex the board and damage internal traces. The wireless charging IC (Iktara), baseband PMU, and baseband CPU all sit under this shield. Once the shield is removed, this chip is fairly easy to replace and usually fixes the problem.

Migrated from old wiki
