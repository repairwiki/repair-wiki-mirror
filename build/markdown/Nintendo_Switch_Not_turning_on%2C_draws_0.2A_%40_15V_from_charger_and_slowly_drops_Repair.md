---
title: "Nintendo Switch Not turning on, draws 0.2A @ 15V from charger and slowly drops Repair"
pageid: 903
revid: 2197
kind: repair_guide
source: "https://repair.wiki/w/Nintendo_Switch_Not_turning_on,_draws_0.2A_@_15V_from_charger_and_slowly_drops_Repair"
history: "https://repair.wiki/index.php?title=Nintendo_Switch_Not_turning_on,_draws_0.2A_@_15V_from_charger_and_slowly_drops_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=2197"
last_edited: "2024-01-13T14:34:35Z"
contributors:
  - "ASRepairs"
  - "HaileyKitty"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Nintendo Switch"
  - "Stubs"
infobox:
  Device: "Nintendo Switch"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "multimeter, soldering iron, soldering station, BGA rework station"
  Type: "BGA, Soldering"
  Difficulty: "4. Specialist"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Nintendo Switch Not turning on, draws 0.2A @ 15V from charger and slowly drops Repair

## Problem description
Repairing of a problem characterized by no power, drawing only 0.2A @ 15V from the charger and slowly drops. Without the battery plugged it, it draws ~0.275A @ 15V

## Symptoms
- Not turning on
- Draws 200mA at 15V from charger and slowly drops, unplugging battery draws around 0.275A @ 15V

## Solution
Likely dead CPU. Check if the infamous [https://repair.wiki/w/Nintendo_Switch_CPU_capacitors#SOT-323-6_IC_near_MAX17050 CPU cap near M92T36] is shorted. If it is, currently the only possible reason is a dead CPU. There might be corrosion or burn marks near MAX17050. There is another [https://repair.wiki/w/Nintendo_Switch_CPU_capacitors#SOT-323-6_IC_near_MAX17050 CPU cap near the SOT-323-6 IC close to MAX17050], if that is shorted as well then you can easily assume the motherboard is unrecoverable. Can be further confirmed by shorted capacitors around the MAX PMICs [source coming soon - ItalianRetroGuy]
