---
title: "S27A950D Will not power on and no status light Repair"
pageid: 1040
revid: 2454
kind: repair_guide
source: "https://repair.wiki/w/S27A950D_Will_not_power_on_and_no_status_light_Repair"
history: "https://repair.wiki/index.php?title=S27A950D_Will_not_power_on_and_no_status_light_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=2454"
last_edited: "2024-01-14T12:30:43Z"
contributors:
  - "ASRepairs"
  - "HaileyKitty"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Samsung SyncMaster SA950"
  - "Stubs"
infobox:
  Device: "Samsung SyncMaster SA950"
  Affects_parts: "Logic Board"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# S27A950D Will not power on and no status light Repair

## Problem description
Model: S27A950D

Board Code: BN41-01668

Won't power on. Status led does not illuminate when plugged in.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Won't power on.
- Status led does not illuminate when plugged in.

## Solution
- Check the power rails. On the bottom of the board there are test points. 3.3 and 1.26 must be present for the status display to illuminate.
- There are two buck converters near the power input. These are driven by the Z1033AI ICs "IC204" and "IC202". On my board the 1.26 supply IC was not working and had to be replaced.

If you inject voltage to this circuit, it should draw about 5mA with the device off. When the device is powered on the supply will draw 400-500 mA. After injecting 1.26v the button panel lights up. There is also a fuse "F202" on the output of the 1.26 supply, check this if you have power on the output but the panel still doesn't light up.
