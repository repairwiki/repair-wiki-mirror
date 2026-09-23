---
title: "Simco ChargeMaster Medium not turning on repair"
pageid: 1940
revid: 4174
kind: repair_guide
source: "https://repair.wiki/w/Simco_ChargeMaster_Medium_not_turning_on_repair"
history: "https://repair.wiki/index.php?title=Simco_ChargeMaster_Medium_not_turning_on_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=4174"
last_edited: "2024-06-30T07:29:01Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Simco ChargeMaster Medium"
  - "Stubs"
infobox:
  Device: "Simco ChargeMaster Medium"
  Affects_parts: "Main switching transformer"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering, Teardown, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Simco ChargeMaster Medium not turning on repair

## Problem description
Fixing the ChargeMaster Medium that doesn't turn on, does not pull any current, and does not react to power. This particular issue is related to the main DC-DC transformer being faulty. This is a rather common issue with this device since the DC-DC circuit does not use any smart IC to reglaute it but rather an analog circuit to drive the switching MOSFETs that switch the transformer.
![Main power board, transformer on the top right (Figure 1)](images/c/c4/20240627_140518.jpg)

## Symptoms
- Doesn't turn on.
- No reaction to input AC power
- Screen always off
- ==Solution==
This issue was rather hard to diagnose since there aren't any ICs that you can check the various pins of. After checking if the MOSFETs are not shorted, the resistors/diodes/caps are within spec, the only thing left to check was the transformer. There's currently no way to buy a replacement transformer, the only way is to open it up, unwind the wires making note of the number of turns, and then replace the windings with a slightly thicker wire. This problem occurs because the transformer heats up beyond its rated specification which cause the enamel on the windings to break and short them.

If the issue has a single, specific solution, provide it in this section and delete the sub-headers below. Otherwise, if there are multiple potential causes for the problem, outline the process of identifying the root cause and offer corresponding solutions below.

### Diagnostic Steps
### Repair Steps
