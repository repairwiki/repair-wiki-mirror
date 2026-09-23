---
title: "Micro Master 430 low DC voltage reading repair"
pageid: 1876
revid: 4057
kind: repair_guide
source: "https://repair.wiki/w/Micro_Master_430_low_DC_voltage_reading_repair"
history: "https://repair.wiki/index.php?title=Micro_Master_430_low_DC_voltage_reading_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=4057"
last_edited: "2024-06-11T12:48:07Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Micro Master 430 6SE6430-2UD31-5CA0"
infobox:
  Device: "Micro Master 430 6SE6430-2UD31-5CA0"
  Affects_parts: "Opamp-LM358"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Micro Master 430 low DC voltage reading repair

## Problem description
Diagnosing and fixing an issue with Siemens micromaster 430 where the DC link measurement inside the inverter measures too low (figure 1) or too high even though in reality when measured with a multimeter it's within normal range.
![Example faulty measurement in Siemens Drive Monitor (figure 1)](images/6/6b/20240611_130121.jpg)
![DC link measurement circuit -Lm358m opamp- (figure 2)](images/1/14/20240611_115741.jpg)
![Measurement after replacing the opamp- (figure 3)](images/d/d1/20240611_131623.jpg)

## Symptoms
- Low/high DC voltage measurement on BOP panel/Drive Monitor
- Fault F0002/F0003
- Unclear-able fault

- - ==Solution==
Measure the sensing blue resistors (figure 2) outside the circuit. They're 6.8 mega ohms. If one or both is blown, replace them. If they're okay, measure the SMD resistors around the op amp, if they're also fine, check the capacitors if one is shorted, if all of those components are functioning, replace the op amp (LM358m). In this case, the op amp was faulty. Upon replacement, the inverter started measuring properly (figure 3).
