---
title: "MacBook Pro A1707 Charger stuck at 5V instead of 20V repair"
pageid: 193
revid: 3693
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1707_Charger_stuck_at_5V_instead_of_20V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1707_Charger_stuck_at_5V_instead_of_20V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3693"
last_edited: "2024-03-21T09:37:34Z"
contributors:
  - "ASRepairs"
  - "IFixNC Beau"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1707"
infobox:
  Device: "MacBook Pro A1707"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1707 Charger stuck at 5V instead of 20V repair

## Problem description
Charging voltage from USB-C charger is stuck at 5V instead of 20V.

For more information about this problem, check [Charger stuck at 5V instead of 20V on MacBooks](Charger_stuck_at_5V_instead_of_20V_on_MacBooks.md)
![C7080 capacitor on boardview (Figure 1)](images/9/94/Screen_Shot_2024-03-18_at_2.12.15_PM.png)

## Symptoms
- Not charging
- Most likely not turning on
- Drawing very little to no current
## Solution
- If 5 V and 0.00 A draw, most likely a 0–1 Ω short to ground on PP3V3_G3H
- PP3V3_G3H missing due to a short circuit on the input to PP3V3_G3H creation circuit
- Corroded LDO cap for PP3V3_G3H around a CD3215. On right side of board, check under shielding by SSD under the right CD3215 for hidden corroded cap. [https://www.youtube.com/watch?v=G1pSqm97j6s Example video]: (drawing 200 mA, 1 V on PP3V3_G3H, not possible to measure short to ground on PP3V3_UPC_LDO because it is only bringing PP3V3_G3H down when machine is turned on)
- PP3V3_G3H missing due to PM_EN_P3V3_G3H missing due to bad ISL9239
- CD 3215 chip does not receive a signal to request 20 V from the charger. Issue should be traced back along the line to identify culprit, which is often ISL 9239.

- Bad CD3215
- A bad CD3215 will not boot loop, whereas the good CD3215 WILL boot loop. It takes up to 10 seconds for it loop, so be patient.
- Check voltage at C7080. If it reads ~1.4v, it's most likely a CD3215.
- Bad CD3215 ROM chip (U2890)
- CD3215 had corrosion nearby, fixed by cleaning up the area and reflowing [https://www.youtube.com/watch?v=wPMV38TygnA Example video]: (corroded capacitor next to CD3215, fixed by reflow of CD3215 and replaced capacitor)
- CD3215 liquid damaged. Attempt to reflow affected chip(s) first. Replace the chip(s) if reflowing does not resolve the issue.
- Bad / dead ISL9239 — it needs to make the enable for the 3.3 V regulator (U6990), PM_EN_P3V3_G3H
- Bad / dead SMC — it needs to talk to the CD3215s to tell them to go to 20 V
[https://www.youtube.com/watch?v=7-fmZX4FcNc Example video]
