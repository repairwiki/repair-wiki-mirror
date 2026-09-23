---
title: "Nintendo Switch Joycons not charging or connecting Repair"
pageid: 921
revid: 2239
kind: repair_guide
source: "https://repair.wiki/w/Nintendo_Switch_Joycons_not_charging_or_connecting_Repair"
history: "https://repair.wiki/index.php?title=Nintendo_Switch_Joycons_not_charging_or_connecting_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=2239"
last_edited: "2024-01-13T16:44:12Z"
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
  Affects_parts: "JoyCons"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Nintendo Switch Joycons not charging or connecting Repair

![Diagram showing resistor layout (Figure 1)](images/6/6d/1200px-Joycon_DCDC_cap_diagram.jpg)
## Problem description
Fixing an issue where the Joycons are not charging or connecting/pairing. Joycons aren't charging (on one or both sides), the fan works, and the side-rail is confirmed working.
## Symptoms
- Joycons not charging or connecting/pairing
- Joycons aren't charging (on one or both sides)
- The fan works
- The side-rail is confirmed working.

## Solution
![Right Joycon DC-DC converter (Figure 3)](images/5/59/1041px-Right_Joycon_DC-DC_converter.jpg)![Left Joycon DC-DC converter (Figure 2)](images/1/1b/1200px-Left_Joycon_DC-DC_converter.jpg)Measure both resistors. 18kohm on both resistors (Figure 1) indicates a failed/shorted capacitor (even if the cap does not test as a short). Resistors should measure 100kohm and 22kohm respectively.

Measure pin 6 (Figure 2 & 3) in diode mode-- it should read 0. If it reads 0.6v drop this reinforces the capacitor failure.

If resistors check out, the DC-DC component may need replacing
