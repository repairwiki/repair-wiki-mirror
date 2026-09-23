---
title: "Short on 12V or 3.3V rail on Pascal (GTX 1000) GPUs Repair"
pageid: 334
revid: 3654
kind: repair_guide
source: "https://repair.wiki/w/Short_on_12V_or_3.3V_rail_on_Pascal_(GTX_1000)_GPUs_Repair"
history: "https://repair.wiki/index.php?title=Short_on_12V_or_3.3V_rail_on_Pascal_(GTX_1000)_GPUs_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3654"
last_edited: "2024-03-16T10:18:09Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
infobox:
  Device: "GTX 1070, GTX 1070Ti, GTX 1080, GTX 1080Ti, GTX 1060"
  Affects_parts: "Whole board"
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Short on 12V or 3.3V rail on Pascal (GTX 1000) GPUs Repair

## Problem description
When the card is not turning on at all, causes the entire computer not to turn on. Caused by a shorted component on 12V or 3.3V rail.
![12V_Bus possible shorted components. (Figure 1)](images/3/3c/Possible_shorts_on_12V_BUS_Pascal.jpg)

## Symptoms
- Sub 100 Ω on the 12V_Bus, 12V_EXT, or 3.3V_BUS.
- Computer won't power on or instantly shutting down upon pressing the power button.
- Fans not spinning (in case of blown fuse).
![12V_EXT possible shorted components. (Figure 2)](images/7/78/Possible_shorts_on_12V_EXT_Pascal.jpg)
![3.3V_BUS possible shorted components. (Figure 3)](images/3/3f/Front_3.3_short_pascal.jpg)

## Solution
### Diagnostic Steps
[How to find short circuits](How_to_find_short_circuits.md)

- Identify which rail is shorted by measuring the resistance of each. [Pascal GPU Diagnosing Guide](Nvidia_Pascal_GPU_Diagnosing_Guide.md) here you can find points to measure from
- Inject 1V 10A to the shorted rail
- Check with thermal camera or isopropyl alcohol for hotspots, all possible shorts are in the attached photos.
- In the case of 12V short, make sure to measure VCore voltage while injecting, if you read any voltage higher than 0.1V then a [MOSFET](Transistors_-_Repair_Basics.md) is likely shorting 12V to the GPU then to GND.
  - If this is the case, remove the ground power supply lead and connect it to VCore. Then identify the shorted MOSFET/Power Stage.

### Repair Steps
- After the shorted component has been identified, remove it.
  - If the short is still present, repeat the diagnostic steps until you find the other shorted component.
- If the short is gone after removing the component, replace it.
  - In the case where the shorted component was a MOSFET and after replacing it shorts again immediately, replace the controller/driver for this MOSFET.
