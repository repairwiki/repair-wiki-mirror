---
title: "MacBook Pro A1502 2013-2014 Not turning on (19.5 V 100–200 mA on charger) repair"
pageid: 490
revid: 1022
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1502_2013-2014_Not_turning_on_(19.5_V_100%E2%80%93200_mA_on_charger)_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1502_2013-2014_Not_turning_on_(19.5_V_100%E2%80%93200_mA_on_charger)_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=1022"
last_edited: "2023-11-08T17:59:42Z"
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

# MacBook Pro A1502 2013-2014 Not turning on (19.5 V 100–200 mA on charger) repair

## Problem description
#incomplete
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- MacBook not turning on.
- Only drawing between 100 to 200 mA on charge port.

## Solution
As usual check PPBUS_G3HOT, PPVRTC_G3H, PP5V_S5

PP5V_S4 is 0 V (problem here)

C7320 has corroded pad so U7320 had no input on pin 6 so no Vcore was being produced on one of the power phases.

Redoing the corroded trace with a jumper wire and replacing the U7320 chip solved the problem.

[https://www.youtube.com/watch?v=8s7HBtQYcaM Video example]
