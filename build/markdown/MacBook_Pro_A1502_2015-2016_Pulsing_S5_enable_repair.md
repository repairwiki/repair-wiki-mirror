---
title: "MacBook Pro A1502 2015-2016 Pulsing S5 enable repair"
pageid: 477
revid: 994
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1502_2015-2016_Pulsing_S5_enable_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1502_2015-2016_Pulsing_S5_enable_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=994"
last_edited: "2023-11-08T13:07:09Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1502"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1502"
  Affects_parts: "Whole board"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1502 2015-2016 Pulsing S5 enable repair

## Problem description
A short on any capacitor in PP5V_S3 rail can cause S5 enable to pulse.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Pulsing enable for S5

## Solution
Check C6412 (or any other cap in PP5V_S3) for a PP5V_S0 audio short to ground. This can cause S5 enable and everything above it to pulse.
