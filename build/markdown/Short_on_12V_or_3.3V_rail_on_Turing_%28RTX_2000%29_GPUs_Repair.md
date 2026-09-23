---
title: "Short on 12V or 3.3V rail on Turing (RTX 2000) GPUs Repair"
pageid: 426
revid: 3652
kind: repair_guide
source: "https://repair.wiki/w/Short_on_12V_or_3.3V_rail_on_Turing_(RTX_2000)_GPUs_Repair"
history: "https://repair.wiki/index.php?title=Short_on_12V_or_3.3V_rail_on_Turing_(RTX_2000)_GPUs_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3652"
last_edited: "2024-03-16T10:18:00Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for RTX 2060"
  - "Repair guides for RTX 2070"
  - "Repair guides for RTX 2080"
  - "Repair guides for RTX 2080Ti"
  - "Stubs"
infobox:
  Device: "RTX 2060, RTX 2070, RTX 2080, RTX 2080Ti"
  Affects_parts: "Whole board"
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Short on 12V or 3.3V rail on Turing (RTX 2000) GPUs Repair

## Problem description
When the card is not turning on at all, causes the entire computer not to turn on. Caused by a shorted component on 12V or 3.3V rail.
![Possible shorted components for 12V_BUS on a FE 2080. Front side (Figure 1)](images/2/29/Turing_12v_bus_shorts_front.jpg)

## Symptoms
- Sub 100 Ω on the 12V_Bus, 12V_EXT, or 3.3V_BUS.
- Computer won't power on or instantly shutting down upon pressing the power button.
- Fans not spinning (in case of blown fuse).

![Possible shorted components for 12V_BUS on a FE 2080. Back side (Figure 2)](images/1/16/Turing_12v_bus_shorts_back.jpg)
![Possible shorted components for 12V_EXT on a FE 2080. Front side (Figure 3)](images/6/6e/Turing_12v_ext_shorts_front.jpg)
![Possible shorted components for 12V_EXT on a FE 2080. Back side (Figure 4)](images/8/83/Turing_12v_ext_shorts_back.jpg)
![Possible shorted components for 3.3V_BUS on a FE 2080 (Figure 5)](images/b/be/Turing_3.3v_shorts.jpg)

## Solution
### Diagnostic Steps
[How to find short circuits](How_to_find_short_circuits.md)
- Identify which rail is shorted by measuring the resistance of each. [Turing GPU Diagnosing Guide](Nvidia_Turing_GPU_Diagnosing_Guide.md) here you can find points to measure from
- Inject 1V 10A to the shorted rail
- Check with thermal camera or isopropyl alcohol for hotspots, all possible shorts are in the attached photos.
- In the case of 12V short, make sure to measure VCore voltage while injecting, if you read any voltage higher than 0.1V then a [MOSFET](Transistors_-_Repair_Basics.md) is likely shorting 12V to the GPU then to GND.
  - If this is the case, remove the ground power supply lead and connect it to VCore. Then identify the shorted MOSFET/Power Stage.
### Repair Steps
- After the shorted component has been identified, remove it.
  - If the short is still present, repeat the diagnostic steps until you find the other shorted component.
- If the short is gone after removing the component, replace it.
  - In the case where the shorted component was a MOSFET and after replacing it shorts again immediately, replace the controller/driver for this MOSFET.
