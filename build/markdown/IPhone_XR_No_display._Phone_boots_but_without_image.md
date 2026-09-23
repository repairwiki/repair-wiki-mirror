---
title: "IPhone XR No display. Phone boots but without image"
pageid: 3830
revid: 6695
kind: repair_guide
source: "https://repair.wiki/w/IPhone_XR_No_display._Phone_boots_but_without_image"
history: "https://repair.wiki/index.php?title=IPhone_XR_No_display._Phone_boots_but_without_image&action=history"
permalink: "https://repair.wiki/index.php?oldid=6695"
last_edited: "2025-05-14T18:14:30Z"
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

# IPhone XR No display. Phone boots but without image

## Problem description
iPhone XR will power on and you may hear sound or see a normal boot cycle on DCPSU but phone boots with no image
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Common issues & Solutions
- Bad Screen (Rule out screen before continuing)
- Pry Damage. It does happen but not common. If a tech is too rough with their pry tool when disconnecting the screen, it is very easy to damage the FPC connectors. The image filters and caps are covered in overfill, so they do not typically get damaged. Can happen though.
- Short on 5v7 line. 5v7 short is the happy, fixable version of this issue. Can be checked using diode mode on the connector. Most of the 5v7 caps are on the back side next to the NAND on this model (weird) but they tend to short from a drop or flexion damage. If you have a 5v7 short, consider yourself lucky.
- Check C5600 cap on PP_CHESNUT_CP. It has no leg on ground. So check to see if it has continuity across it. If it does, replace it.
  - A cap should NOT have continuity across it.
- Chesnut/CPU issue (not happy/fixable version of repair). It is very common for this model to have no image randomly with no damage or no 5v7 short. Usually, heat on the shields or replacing Chesnut resolves the issue but not for long...most common visual issue is the CPU shield being broken in the bottom right corner by the WiFi IC. This happens from a hard drop or flexion damage. Replacing chesnut is a placebo because it is basically just heating broken traces under the CPU. This temporarily restores image, but it will come back for warranty. True fix is to reball the CPU, but it is not practical. Usually, this is a data only scenario to avoid reworks/warranty repairs. For Data Recovery only, you can temporarily clamp the CPU down & get image long enough to connect to iTunes or 3U tools and run a backup.

Migrated from old wiki
