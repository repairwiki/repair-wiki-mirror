---
title: "Micro Master 440 fault F0022 repair"
pageid: 2126
revid: 4437
kind: repair_guide
source: "https://repair.wiki/w/Micro_Master_440_fault_F0022_repair"
history: "https://repair.wiki/index.php?title=Micro_Master_440_fault_F0022_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=4437"
last_edited: "2024-07-18T11:36:39Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Micro Master 440 6SE6440-2UD31-1CA1"
infobox:
  Device: "Micro Master 440 6SE6440-2UD31-1CA1"
  Affects_parts: "Main power relay"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Micro Master 440 fault F0022 repair

## Problem description
Repairing one of the causes for fault code F0022 "Power stack fault" on Siemens micromaster 440 inverter. This solution concerns the main power relay (figure 1)
![Main power relay (Figure 1)](images/f/f2/20240718_132823.jpg)

## Symptoms
- Works until a certain frequency/power then shows error F0022
- General fault F0022 even before starting the motor
- Shows fault F0022 as soon as starting the motor
- ==Solution==

- First confirm that the main IGBT module is not damaged in any way.
- Measure each individual IGBT as described [here](Transistors_-_Repair_Basics.md).
- If the IGBT module is okay, look under the main power relay.
- In my case, one of the legs was not soldered properly and it was black from overheating.
- Take out the relay and confirm that it's working by injecting voltage on it's coil and measuring the contacts.
- If the relay is working properly, repair the hole for the leg or run a thick wire jumper to where it's supposed to go (the wire on the side going to the adjacent PCB, measure with continuity to confirm which exact one).
- After this the inverter should work properly
