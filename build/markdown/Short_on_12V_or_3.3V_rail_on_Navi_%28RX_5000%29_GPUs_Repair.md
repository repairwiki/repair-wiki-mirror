---
title: "Short on 12V or 3.3V rail on Navi (RX 5000) GPUs Repair"
pageid: 1677
revid: 3677
kind: repair_guide
source: "https://repair.wiki/w/Short_on_12V_or_3.3V_rail_on_Navi_(RX_5000)_GPUs_Repair"
history: "https://repair.wiki/index.php?title=Short_on_12V_or_3.3V_rail_on_Navi_(RX_5000)_GPUs_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3677"
last_edited: "2024-03-16T11:37:05Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for RX 5700"
  - "Repair guides for RX 5700XT"
infobox:
  Device: "RX 5700, RX 5700XT"
  Affects_parts: "Whole board"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Short on 12V or 3.3V rail on Navi (RX 5000) GPUs Repair

## Problem description
Identifying the cause and repairing Navi GPUs when a short on either the 12V or 3.3V (Base rails) line occurs. This causes the entire PC to not turn on because the PSU will be under Over Current Protection (OCP). [Learn more about base voltage rails here](Base_Voltage_Rails_For_GPUs_Explained.md)
![12V_BUS shorts on Navi (Figure 1)](images/9/9c/12v_bus_shorts_on_navi.png)
![Possible 12V_EXT shorts on Navi (Figure 2)](images/8/82/12v_ext_shorts_on_navi.png)
![Possible 3.3V shorts on Navi (Figure 3)](images/c/c7/3.3v_shorts_on_navi.png)

## Symptoms
- Sub 100 Ω on the 12V_Bus, 12V_EXT, or 3.3V_BUS.
- Computer won't power on or instantly shutting down upon pressing the power button.
- Fans not spinning (in case of blown fuse).

## Solution
### Diagnostic Steps
[How to find short circuits](How_to_find_short_circuits.md)
- Identify which rail is shorted by measuring the resistance of each. [Navi GPU Diagnosing Guide](AMD_Navi_%28RX_5000_series%29_GPU_Diagnosing_Guide.md) here you can find points to measure from
- Inject 1V 10A to the shorted rail
- Check with thermal camera or isopropyl alcohol for hotspots, all possible shorts are in the attached photos.
- In the case of 12V short, make sure to measure VCore voltage while injecting, if you read any voltage higher than 0.1V then a [MOSFET](Transistors_-_Repair_Basics.md) is likely shorting 12V to the GPU then to GND.
  - If this is the case, remove the black power supply lead and connect it to VCore. This way you can inject higher voltage without the risk of killing the core.
- In the case of 3.3V short, on the back of the card (not pictured), the two IR35217s use 3.3V as VCC voltage. They could be the culprit, if not, it is either a capacitor or the core itself.
### Repair Steps
- After the shorted component has been identified, remove it.
  - If the short is still present, repeat the diagnostic steps until you find the other shorted component.
- If the short is gone after removing the component, replace it.
  - In the case where the shorted component was a MOSFET and after replacing it shorts again immediately, replace the controller/driver for this MOSFET.
