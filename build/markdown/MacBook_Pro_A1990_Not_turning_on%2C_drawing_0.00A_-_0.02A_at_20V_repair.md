---
title: "MacBook Pro A1990 Not turning on, drawing 0.00A - 0.02A at 20V repair"
pageid: 125
revid: 292
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1990_Not_turning_on,_drawing_0.00A_-_0.02A_at_20V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1990_Not_turning_on,_drawing_0.00A_-_0.02A_at_20V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=292"
last_edited: "2023-10-11T16:34:26Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1990"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1990"
  Affects_parts: "T2 firmware"
  Needs_equipment: "None"
  Type: "Software"
  Difficulty: "1. Easy"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1990 Not turning on, drawing 0.00A - 0.02A at 20V repair

## Problem description
A1990 MacBook not turning on, drawing 0.00A - 0.02A at 20V, PP3V3_G3H_SOCPMU present, but PPVCCPRIMCORE_PRIM_REG and therefore PP3V3_S5 missing.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Not powering on
- Missing PP3V3_S5 and PPVCCPRIMCORE_PRIM_REG voltages
- Only drawing 0.00A - 0.02A at 20V as measured by USB-C meter

## Solution
Do not replace U7800. Instead, put device into DFU mode and select advanced -> repair. [https://support.apple.com/guide/apple-configurator-2/revive-or-restore-an-intel-based-mac-apdebea5be51/mac Read this apple article.]

The problem seems to be T2 not talking to the PMU correctly. Note, you need a battery connected for PMU to work. Best to completely assemble the device.

The 2019 16" model has the same issue.
