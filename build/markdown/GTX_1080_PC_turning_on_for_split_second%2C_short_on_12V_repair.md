---
title: "GTX 1080 PC turning on for split second, short on 12V repair"
pageid: 1703
revid: 3760
kind: repair_guide
source: "https://repair.wiki/w/GTX_1080_PC_turning_on_for_split_second,_short_on_12V_repair"
history: "https://repair.wiki/index.php?title=GTX_1080_PC_turning_on_for_split_second,_short_on_12V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3760"
last_edited: "2024-04-10T10:12:45Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for GTX 1080"
infobox:
  Device: "GTX 1080"
  Affects_parts: "Capacitor, VRM"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# GTX 1080 PC turning on for split second, short on 12V repair

## Problem description
GTX 1080 Zotac, PC not turning on or turning on for split second then turning off when the card is inserted. This particular case concerns a Zotac AMP EXTREME GTX 1080
![Short circuit measurement on 12V_EXT (Figure 1)](images/6/6d/20240410_104859.jpg)

## Symptoms
- Whole computer not starting
- Card not powering up
- Fans flinch for a split second
- Short on 12V as measured by a multimeter
![Vcore VRMs (Figure 2)](images/a/ae/20240410_1155411.jpg)
![Shorted capacitor close up view (Figure 3)](images/f/fd/Screenshot_20240410-105532.jpg)
![Replaced capacitors (Figure 4)](images/2/2a/20240410_111249.jpg)

## Solution
### Diagnostic Steps
- Start by [measuring the resistance of the 12V lanes](Nvidia_Pascal_%28GTX_1000%29_GPU_Diagnosing_Guide.md) (12V_BUS, 12V_EXT)
- If you suffer from the same problem, you should measure sub 100 Ohms on one of them, follow this [guide for potential shorted components](Short_on_12V_rail_on_Pascal_%28GTX_1000%29_GPUs_Repair.md)
  - In this case, a short was found on one of the 12V_EXT connectors (Figure 1)
- After identifying which rail is [shorted](Short_Circuits_-_Repair_Basics.md), inject voltage (1V 10A) to localize the shorted component
  - The most obvious suspects are the VCore VRMs/MOSFETS shown in figure 2
    - However the actual shorted component turned out to be a capacitor on the other side under the Vcore VRMs. The culprit was C195. C196 looked suspicious as well. (Figure 3,4)

### Repair Steps
Simply de-solder the shorted capacitor. It is not strictly necessary to replace it. However, it's value and rating are 16V 10 uF 0603 package. If the source of the short is a VRM, then you must replace it!

After removing the shorted component, measure again to confirm the short is gone, if not, repeat the steps to find the other short.
