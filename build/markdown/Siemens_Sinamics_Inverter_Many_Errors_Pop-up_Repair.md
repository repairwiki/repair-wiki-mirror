---
title: "Siemens Sinamics Inverter Many Errors Pop-up Repair"
pageid: 2580
revid: 5198
kind: repair_guide
source: "https://repair.wiki/w/Siemens_Sinamics_Inverter_Many_Errors_Pop-up_Repair"
history: "https://repair.wiki/index.php?title=Siemens_Sinamics_Inverter_Many_Errors_Pop-up_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=5198"
last_edited: "2024-11-05T14:56:03Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Missing device page"
  - "Repair guide"
  - "Repair guides for Sinamics 6SL3120-1TE23-0AA3"
  - "Repair guides for Sinamics 6SL3120-2TE15-0AA4"
  - "Repair guides for Sinamics 6SL3120-2TE21-0AA4"
infobox:
  Device: "Sinamics 6SL3120-2TE15-0AA4, Sinamics 6SL3120-1TE23-0AA3, Sinamics 6SL3120-2TE21-0AA4"
  Affects_parts: "DC-DC transformer (VAC 5046X005"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Siemens Sinamics Inverter Many Errors Pop-up Repair

## Problem description
This guide concerns most Siemens Sinamics inverters with similar board to Figure 1. The issue happens suddenly and unexpectedly. Many Errors appear (it varies between inverters and which part is faulty)
![Main board (figure 1)](images/b/b1/20241105_150141.jpg)
![Good trafo measurement (figure 2)](images/8/87/20241105_150438.jpg)
![Failed trafo measurement (figure 3)](images/c/cc/20241105_150414.jpg)
![Under the transformer, after soldering the broken wire (figure 4)](images/0/05/20241105_150649.jpg)

## Symptoms
- Multiple errors
- Can not clear errors
- Physically good components, no visible damage
- == Solution ==

To solve this issue, you need to identify if this guide is for your specific problem first.

### Diagnostic Steps
- Open up the inverter
- Check for any physical damage such as blown up [IGBT](Transistors_-_Repair_Basics.md)
- If there is any physical damage, this guide is not for you.
- If there is no physical damage, measure all the transformes on the board like in figure 2, if you read near 0 Ohm, it's good measurement, if it is higher or OL (figure 3), then you have a cut off inductor. Proceed to repair steps.

### Repair Steps
You can just buy and replace the transformer and that will fix the issues. If you can't buy it or it is not available, you can fix it yourself.

The reason those transformers usually fail is not because of too much current but because they're filled with resin and with many cycles of heating up and cooling down the wire outside the resin gets pulled from the resin and it cuts it off (figure 4) you can just solder it again and it will work again.
