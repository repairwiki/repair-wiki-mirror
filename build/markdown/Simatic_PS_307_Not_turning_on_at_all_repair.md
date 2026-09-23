---
title: "Simatic PS 307 Not turning on at all repair"
pageid: 2007
revid: 4266
kind: repair_guide
source: "https://repair.wiki/w/Simatic_PS_307_Not_turning_on_at_all_repair"
history: "https://repair.wiki/index.php?title=Simatic_PS_307_Not_turning_on_at_all_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=4266"
last_edited: "2024-07-09T10:25:57Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Simatic PS 307"
infobox:
  Device: "Simatic PS 307"
  Affects_parts: "TVS 1.5KE200CA, fuse"
  Needs_equipment: "multimeter, soldering iron, soldering station, LBPSU"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Simatic PS 307 Not turning on at all repair

## Problem description
Repairing Siemens Simatic PS 307 industrial power supply that doesn't turn on when powered. This particular issue is associated with a blown fuse and a [shorted](Short_Circuits_-_Repair_Basics.md) TVS [diode](Diodes_-_Repair_Basics.md).
![Shorted diode, 1.5KE200CA (Figure 1)](images/b/bf/20240709_093224.jpg)

## Symptoms
- Not reacting to power when plugged in
- No output voltage
- No LED lights turning on

- - ==Solution==

### Diagnostic Steps
- Disassemble the device
- Measure with a multimeter the legs of the full bridge rectifier, if you have short on + and - then you have a different issue, if you measure a short on either +- and the ~~ pins, then you also have a different problem, the rectifier might be shorted
- For this issue, you should measure a short between both ~~ pins on the rectifier and a blown fuse
- If that's the case, inject voltage into the pins and check what gets hot
- In this case, it was the diode in figure 1

### Repair Steps
Desolder the diode and check if the short is gone, if so, replace it along with the fuse with new ones and test if that fixes it. In this case, that was all it and after replacement the power supply started working again.
