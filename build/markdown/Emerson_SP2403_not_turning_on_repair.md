---
title: "Emerson SP2403 not turning on repair"
pageid: 1851
revid: 4088
kind: repair_guide
source: "https://repair.wiki/w/Emerson_SP2403_not_turning_on_repair"
history: "https://repair.wiki/index.php?title=Emerson_SP2403_not_turning_on_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=4088"
last_edited: "2024-06-15T05:52:14Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Emerson SP2403"
infobox:
  Device: "Emerson SP2403"
  Affects_parts: "D18 diode (PR 1600)"
  Needs_equipment: "multimeter, soldering iron, soldering station."
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Emerson SP2403 not turning on repair

## Problem description
Diagnosing and fixing an issue with an Emerson SP2403 inverter that does not turn on or react to power when connected to 3 phase 400V AC
![Location of D18 diode and the TR18 MOSFET (Figure 1)](images/8/8f/20240610_140438.jpg)

## Symptoms
- Not turning on.
- Not reacting to power.
- MOSFET gate switching for split second then stopping and repeating when measured with an oscilloscope.
- VCC for UC2844B going up to 16V then dropping to 7V and raising again on a loop.
- - ==Solution==
Measure D18 diode in with a multimeter in diode mode. Make sure it measures 0.4-0.7V, anything less or more and it's dead. In this case it was 0.1V on both ways which indicates that it's dead. The original diode was a PR1600. A photoflash rectifier diode with 1600v reverse voltage. I've replaced it with a rectifying diode with 1kV reverse voltage and it started switching properly again and working.
