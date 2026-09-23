---
title: "GTX 1080Ti Not detected repair (Short on 1.8V)"
pageid: 1967
revid: 4912
kind: repair_guide
source: "https://repair.wiki/w/GTX_1080Ti_Not_detected_repair_(Short_on_1.8V)"
history: "https://repair.wiki/index.php?title=GTX_1080Ti_Not_detected_repair_(Short_on_1.8V)&action=history"
permalink: "https://repair.wiki/index.php?oldid=4912"
last_edited: "2024-09-21T23:15:23Z"
contributors:
  - "ASRepairs"
  - "Galkinvv"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for GTX 1080"
  - "Repair guides for GTX 1080Ti"
  - "Repair guides for GTX 1080Ti SC2 Hybrid"
infobox:
  Device: "GTX 1080Ti, GTX 1080Ti SC2 Hybrid, GTX 1080"
  Affects_parts: "Capacitor C83 22uF 6.3V 0603"
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera."
  Type: "Soldering, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# GTX 1080Ti Not detected repair (Short on 1.8V)

## Problem description
Repairing a problem on a GTX 1080Ti SC2 Hybrid from EVGA where the card is not recognized by the system but it does turn on. This particular issue was caused by a short on 1.8V rail. Usually shorts on that rail are often caused by a failed GPU core and is unrepairable outside of replacing the core. This time however, it was a shorted capacitor.
![Short circuit measurement on 1.8V rail on EVGA 1080Ti SC2 Hybrid (Figure 1)](images/4/44/20240703_130602.jpg)
![Shorted C83 Capacitor 22uF 6.3V 0603 (Figure 2)](images/b/be/20240703_130453.jpg)
![Thermal camera view of the capacitor while injecting voltage (Figure 3)](images/f/fb/20240703_130428.jpg)

## Symptoms
- Card is not detected by the motherboard
- Fan does not spin

## Solution
### Diagnostic Steps
- Disassemble the card
- With your multimeter, measure the resistances of the voltage rails, refer to [this](GTX_1080Ti_SC2_Hybrid.md) or [this](Nvidia_Pascal_%28GTX_1000%29_GPU_Diagnosing_Guide.md) page for reference measurements
- You should measure a [short circuit](Short_Circuits_-_Repair_Basics.md) on [1.8V rail](1.8V_Rail_on_Pascal_GPUs_Explained.md) (Figure 1), if not, this guide is not applicable to your problem
- Inject 1V to the rail and see what heats up using a thermal camera or other short finding methods.
  - In this case, it was a capacitor under the core (Figure 2, 3)
  - You might have a different capacitor that is shorted or the core itself, if you feel the core itself is getting warm, it's a dead core.

### Repair Steps
Simply de-solder the old capacitor and measure if the short is gone, if it is gone then replace it with another (22uF 6.3V 0603). Stress test the card after and reassemble.

If the short is not gone after de-soldering, the core could be dead, repeat the diagnostic steps.
