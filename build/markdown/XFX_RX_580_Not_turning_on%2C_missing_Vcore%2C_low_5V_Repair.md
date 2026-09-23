---
title: "XFX RX 580 Not turning on, missing Vcore, low 5V Repair"
pageid: 1214
revid: 3429
kind: repair_guide
source: "https://repair.wiki/w/XFX_RX_580_Not_turning_on,_missing_Vcore,_low_5V_Repair"
history: "https://repair.wiki/index.php?title=XFX_RX_580_Not_turning_on,_missing_Vcore,_low_5V_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3429"
last_edited: "2024-02-13T16:54:56Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for RX 480"
  - "Repair guides for RX 580"
  - "Repair guides for RX 590"
infobox:
  Device: "RX 480, RX 580, RX 590"
  Affects_parts: "5V LDO LM1117"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# XFX RX 580 Not turning on, missing Vcore, low 5V Repair

## Problem description
Fixing a rare issue with the XFX RX 580 where Vcore/VDDCI are missing but EN and VCC are present. This particular issue is concerned with low 5V voltage.
![5V LDO (LM1117-AD) on XFX RX 580 (Figure 1)](images/9/94/LM1117_on_580_xfx.jpg)

## Symptoms
- Missing VDDCI/Vcore
- Core not heating up/detected
- Less than 4.7V on 5V rail

## Solution
### Diagnostic Steps
- Measure the voltage present at the [5V Rail](5V_Rail_on_Polaris_GPUs_Explained.md)
  - Voltage less than 4.75V will let other rails rise but not [VCore Rail](VCore_Rail_on_Polaris_GPUs_Explained.md), as the [https://media.digikey.com/pdf/Data%20Sheets/ON%20Semiconductor%20PDFs/NCP81022.pdf NCP81022] requires at least 4.75V on its VCC pin. Refer to the repair steps below.
- If you measure 5V at the 5V rail, and EN voltage is around 3V and still no output on Vcore, you have another issue.

### Repair Steps
- If you're measuring less than 4.75V on 5V rail, simply replace the 5V controller (Figure 1) on this card. It is the [https://eu.mouser.com/c/?q=lm1117 LM1117] LDO.
- This will enable the Vcore controller to work, verify by measuring Vcore, should be around 0.8V.
  - If not, check other repair guides on the card's device page. You have another issue.
- If that's the case, assemble the card and stress test.
