---
title: "VCore Rail on Turing GPUs Explained"
pageid: 440
revid: 940
kind: explanatory_guide
source: "https://repair.wiki/w/VCore_Rail_on_Turing_GPUs_Explained"
history: "https://repair.wiki/index.php?title=VCore_Rail_on_Turing_GPUs_Explained&action=history"
permalink: "https://repair.wiki/index.php?oldid=940"
last_edited: "2023-11-07T22:01:41Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for RTX 2060"
  - "Explanatory guides for RTX 2070"
  - "Explanatory guides for RTX 2080"
  - "Explanatory guides for RTX 2080Ti"
infobox:
  Device: "RTX 2060, RTX 2070, RTX 2080, RTX 2080Ti"
  Type: "Circuit"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# VCore Rail on Turing GPUs Explained

Everything you need to know about VCore on Turing GPUs from a repair perspective.

## The Controller Circuit
Most of the time, high end Turing cards (2070-2080Ti) use [https://www.sekorm.com/doc/2032865.html UP9512P]  or the [https://www.monolithicpower.com/en/documentview/productdocument/index/version/2/document_type/Datasheet/lang/en/sku/MP2886AGU/ MP2886a] 8-phase buck controllers (full datasheet is unavailable publicly).

Some low end cards (such as the 2060) use a different variant of the UP9512, the UP9512s (also has no public datasheet) shown in figure 3.
![Vcore controller (UP9512P) location on a reference RTX 2080 (Figure 1).](images/0/03/2080_vcore_on_board.jpg)
![Schematic view of the Vcore circuit (UP9512P) (Figure 2).](images/e/ee/2080_vcore_schematic_up9512p.png)
![Schematic view of the Vcore circuit (UP9512s) (Figure 3).](images/f/f6/2080_vcore_schematic_up9512s.png)
![Vcore enable signal schematic view (Figure 4).](images/5/5e/2080_vcore_enable.png)

Markings on the schematic and board could differ from GPU model to another but the circuit is almost always the same.

VCC is provided to the controller by [5V Rail on Turing GPUs](5V_Rail_on_Turing_GPUs_Explained.md) through a 2 ohm resistor on pin 12 for the P and MP2886a variants and pin 10 on the S variant.

PGOOD signal from the controller then goes to enable PEX and VMem.

## Usage
VCore, as the name suggests, powers on the core. It is the most powerful and most power hungry rail on the card.

The controller generates PWM signals regulating the voltage going to the core depending on the load.

## Common Problems
### No VCore Voltage
In this case, check if the controller has 5V or 3.3V on its VCC, and 3V on EN. If one of them is missing trace their respective circuits and check for broken, knocked off, or defective components

If both are present but no output, measure the Vᵣₑf pin. It should be 2V if not, the controller is faulty.

### No PGOOD  Signal
If the controller isn't outputting PGOOD but VCore is present then it's highly likely the controller itself is faulty.

### Short on VCore
By design, VCore has low resistance to GND (less than 1 Ω), so using a low-end multimeter won't be able to measure it accurately. Often times, the short happens on one of the VRMs. How to find them is explained here [Base Voltage Rail Short on Turing GPUs](Short_Circuits_-_Repair_Basics.md).
