---
title: "MacBook Pro A1502 No green light on charger repair"
pageid: 471
revid: 1011
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1502_No_green_light_on_charger_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1502_No_green_light_on_charger_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=1011"
last_edited: "2023-11-08T17:52:02Z"
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

# MacBook Pro A1502 No green light on charger repair

## Problem description
#incomplete
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Green light on charger not turning on

## Solution
This problem has multiple causes:

- ADAPTER_SENSE not 3 V due to bad DC in board. 16–20 V on ADAPTER_SENSE means charger voltage is leaking into ADAPTER_SENSE, below 2 V means it is missing usually due to a bad DC In board.
- PP3V42_G3H missing
- SMC not working(if SMC is off, you will have 12.23 V on PPBUS_G3H instead of 12.56 V) because it is dead, not turning on(SMC_RESET_L low).
- Corrosion of the SMC's solder connections
- Keyboard bad, shorting PP3V42_G3H to ground or power button stuck on.
- Bad U7000
- Bad U7001
- Bad U7100 — indicators: PPBUS_G3H Below 4 V, board taking 40 mA, U7100 getting warm (check via thermal camera)
