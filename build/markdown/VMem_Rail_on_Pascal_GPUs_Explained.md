---
title: "VMem Rail on Pascal GPUs Explained"
pageid: 362
revid: 833
kind: explanatory_guide
source: "https://repair.wiki/w/VMem_Rail_on_Pascal_GPUs_Explained"
history: "https://repair.wiki/index.php?title=VMem_Rail_on_Pascal_GPUs_Explained&action=history"
permalink: "https://repair.wiki/index.php?oldid=833"
last_edited: "2023-11-07T16:44:25Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for GTX 1060"
  - "Explanatory guides for GTX 1070"
  - "Explanatory guides for GTX 1070Ti"
  - "Explanatory guides for GTX 1080"
  - "Explanatory guides for GTX 1080Ti"
infobox:
  Device: "GTX 1060, GTX 1070, GTX 1070Ti, GTX 1080, GTX 1080Ti"
  Type: "Circuit"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# VMem Rail on Pascal GPUs Explained

Vmem voltage rail on Pascal GPUs explained with most common problems associated with it.
## The controller circuit
![Vmem PWM controller on the board. (Figure 1)](images/5/5e/Pascal_Vmem_controller_on_pcb.png)
![Vmem schematic view. (Figure 2)](images/9/9d/Vmem_pascal_schematic.png)
on most Pascal GPUs, the PWM controller responsible for creating and maintaining Vmem voltage is [https://www.richtek.com/assets/product_file/RT8816A/DS8816A-07.pdf RT8816A] by RICHTEK with marking 7J=YM. It is a dual phase controller.

The controller gets its power from [5V rail](5V_Rail_on_Pascal_GPUs_Explained.md) through 0Ω resistor leading to its 18th pin PVCC.

Enabling this controller is the PGOOD signal from the [PEX PWM controller](PEX_Rail_on_Pascal_GPUs_Explained.md) through 0Ω resistors then to a dual MOSFET Q526 which pulls low the signal that is pulling EN low.

PGOOD from this controller is not used for anything.

Markings on the schematic and board could differ from GPU model to another but the circuit is almost always the same.
## Usage
The controller regulates the voltage going to power the memory modules and the memory controller on the core itself. Switching 12 V to 1.3-1.5V.

Depending on the model and manufacturer of the board and the components used, the PWM signals either go to the VRMs directly or through a driver first.
## Common problems
### No Vmem voltage
Check if the controller has 5 V on its VCC, and around 3 V on EN. If one of them is missing trace their respective circuits and check for broken, knocked off, or defective components

If EN and VCC are present and still no output, check the VREF pin, it should be 2 V. If not, the controller itself might be the culprit.

And if everything seems fine, probe around the controller for shorted caps or malfunctioning resistors.
### Short on Vmem
This is a not a great situation to be in. If you're lucky, a memory module could be shorted, you can check that by injecting 1V to Vmem and applying isopropyl alcohol on the memory chips and see if one or more of the memories are heating up, evaporating the alcohol faster than the rest. Otherwise though, if it's not a shorted capacitor somewhere odds are the core itself is shorted.
