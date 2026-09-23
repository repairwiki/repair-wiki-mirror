---
title: "Nordac SK500E-301-340-A-ERS Not turning on repair"
pageid: 2034
revid: 4298
kind: repair_guide
source: "https://repair.wiki/w/Nordac_SK500E-301-340-A-ERS_Not_turning_on_repair"
history: "https://repair.wiki/index.php?title=Nordac_SK500E-301-340-A-ERS_Not_turning_on_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=4298"
last_edited: "2024-07-10T18:20:55Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Nordac SK500E-301-340-A-ERS"
infobox:
  Device: "Nordac SK500E-301-340-A-ERS"
  Affects_parts: "Vertical PCB, DC-DC circuit"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Nordac SK500E-301-340-A-ERS Not turning on repair

## Problem description
Repairing a problem with this Nordac inverter where the upon connecting it to power, the inverter doesn't turn on or react to it. This issue is cased by a fault in the DC-DC (figure 1) circuit.
![DC-DC circuit on the inverter in the smaller board. (Figure 1)](images/7/7a/20240710_092009.jpg)
![The vertical PCB (Figure 2)](images/e/e0/20240710_091415.jpg)
![DC-DC transformer (Figure 3)](images/9/95/20240710_091645.jpg)

## Symptoms
- Not turning on
- Not reacting to power

## Solution
### Diagnostic Steps
- Disassemble the device, make sure there is no physical damage.
- On the vertical PCB (figure 2), make sure there is no [short circuits](Short_Circuits_-_Repair_Basics.md) on any of the capacitors, if there is any, you need to find where with voltage injection.
- If there are no shorts, measure the power [MOSFET](Transistors_-_Repair_Basics.md), make sure it's working properly.
- If everything is good, confirm the pwm controller is working fine. Find it's datasheet and measure VCC etc.
- If all is good, measure the transformer's windings (Figure 3), the pins that are further from the rest are the primary. In this case it was Open Line which means it is faulty and needs replacement.

### Repair Steps
Replace any faulty components you find. The PWM controller, MOSFET, or transformer. If you look up the transformer's name on eBay, you can find replacement but it's rather expensive. Unfortunately there is no way to regenerate this transformer since it's filled with resin. There's no way to know the number of windings to make a new one either, so the only way is to buy a new one.
