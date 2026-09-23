---
title: "IPhone XR not powering on with heat above the CPU"
pageid: 3834
revid: 6702
kind: repair_guide
source: "https://repair.wiki/w/IPhone_XR_not_powering_on_with_heat_above_the_CPU"
history: "https://repair.wiki/index.php?title=IPhone_XR_not_powering_on_with_heat_above_the_CPU&action=history"
permalink: "https://repair.wiki/index.php?oldid=6702"
last_edited: "2025-05-14T18:31:12Z"
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

# IPhone XR not powering on with heat above the CPU

## Problem description
iPhone XR will not power on.  Before prompt to boot there is heat above the CPU
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- You get 1A or higher current draw before prompt to boot on DC Power Supply
- You feel heat above the CPU

## Solution
- You either have a cracked Speaker Amp (U5002)
- Or a shorted cap on PP_SPKAMP_TOP_VBOOST
- Use a Thermal Cam or Freeze Spray to pin point the root cause of the short
- If Speaker Amp is cracked, replace it
- If you have a shorted cap remove it and then check PP_SPKAMP_TOP_VBOOST with multimeter in diode mode to verify short is no longer present.  You don't need to replace shorted cap if short is no longer present

Migrated from old wiki
