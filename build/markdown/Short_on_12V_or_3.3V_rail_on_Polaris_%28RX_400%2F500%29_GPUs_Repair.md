---
title: "Short on 12V or 3.3V rail on Polaris (RX 400/500) GPUs Repair"
pageid: 386
revid: 3656
kind: repair_guide
source: "https://repair.wiki/w/Short_on_12V_or_3.3V_rail_on_Polaris_(RX_400/500)_GPUs_Repair"
history: "https://repair.wiki/index.php?title=Short_on_12V_or_3.3V_rail_on_Polaris_(RX_400/500)_GPUs_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3656"
last_edited: "2024-03-16T10:18:17Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
infobox:
  Device: "RX 460, RX 470, RX 480, RX 560, RX 570, RX 580, RX 590"
  Affects_parts: "Whole board"
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Short on 12V or 3.3V rail on Polaris (RX 400/500) GPUs Repair

## Problem description
When the card is not turning on at all, causes the entire computer not to turn on. Caused by a shorted component on 12V or 3.3V rail. This page will show where shorts might occur on a Polaris card and how to repair it.
![RX 480 reference. 12V_BUS possible shorts. (Figure 1)](images/a/a0/Polaris_12v_bus_shorts.jpg)

## Symptoms
- Sub 100 Ω on either 12V_BUS, 12V_EXT, or 3.3V_BUS rails.
- Computer won't power on or instantly shutting down upon pressing the power button.
- Fans not spinning (in case of blown fuse).

![RX 480 reference. 12V_BUS possible shorts on the back. (Figure 2)](images/a/a3/Ref_480_12vbus_shorts_back.jpg)
![RX 480 reference. 12V_EXT possible shorts. (Figure 3)](images/1/1f/Ref_480_12vext_shorts_front.jpg)
![RX 480 reference. 3.3V possible shorts. (Figure 4)](images/d/d4/Ref_480_3.3v_shorts_front.jpg)
![RX 480 reference. 3.3V possible shorts on the back. (Figure 5)](images/b/b6/Ref_480_3.3v_shorts_back.jpg)

## Solution
### Diagnostic Steps
[How to find short circuits](How_to_find_short_circuits.md)

  - 12V_BUS is used to power the first phase of VCore, VMem and VDDCI controllers and mosfets/powerstages, Display Rail, and the 5V rail regulator in addition to their input capacitors.**

  - The 12V_EXT rail is mostly used to power the mosfets/powerstages for the Vcore rail. Sometimes, vendors use the 12V_EXT to power 5V regulator instead of the 12V_BUS.**

  - 3.3 V isn't used to feed power-hungry components and therefore is very unlikely to short, but if it does, it's either the Display Rail regulator, 1.8V rail regulator, or the BIOS. it's worth noting that 3.3 goes straight to the GPU core so if it's non of those then it's highly likely the GPU itself is shorted.**
- Identify which rail is shorted by measuring the resistance of each. [Polaris GPU Diagnosing Guide](AMD_Polaris_GPU_Diagnosing_Guide.md) here you can find points to measure from
- Inject 1V 10A to the shorted rail
- Check with thermal camera or isopropyl alcohol for hotspots, all possible shorts are in the attached photos.
- In the case of 12V short, make sure to measure VCore voltage while injecting, if you read any voltage higher than 0.1V then a [MOSFET](Transistors_-_Repair_Basics.md) is likely shorting 12V to the GPU then to GND.
  - If this is the case, remove the ground power supply lead and connect it to VCore. Then identify the shorted MOSFET/Power Stage.
### Repair Steps
- After the shorted component has been identified, remove it.
  - If the short is still present, repeat the diagnostic steps until you find the other shorted component.
- If the short is gone after removing the component, replace it.
  - In the case where the shorted component was a MOSFET and after replacing it shorts again immediately, replace the controller/driver for this MOSFET.
