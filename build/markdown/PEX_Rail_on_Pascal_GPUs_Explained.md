---
title: "PEX Rail on Pascal GPUs Explained"
pageid: 366
revid: 838
kind: explanatory_guide
source: "https://repair.wiki/w/PEX_Rail_on_Pascal_GPUs_Explained"
history: "https://repair.wiki/index.php?title=PEX_Rail_on_Pascal_GPUs_Explained&action=history"
permalink: "https://repair.wiki/index.php?oldid=838"
last_edited: "2023-11-07T16:47:09Z"
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

# PEX Rail on Pascal GPUs Explained

This page talks about the PEX rail on Pascal series of GPUs, how it works, what it's used for, and common problems with it.
## The Controller Circuit
![PEX rail location (Figure 1)](images/2/22/Pex_rail_location_on_pascal.jpg)![PEX schematic (Figure 2)](images/2/29/Pex_schematic_pascal.jpg)![PEX rail usage (Figure 3)](images/6/6b/PEX_rail_usage_on_Pascal_GPUs.jpg)PEX is created by a uP1728Q by uPI semiconductor ([https://datasheetspdf.com/pdf-file/1259305/uPISemiconductor/uP1728/1 datasheet]) or similar IC by stepping down 3.3V to 1V-ish.

Markings on the schematic and board could differ from GPU model to another but the circuit is almost always the same.

The uP1728Q uses 3.3V as Vin coming from the PCIE bus, 5V from [https://repair.wiki/w/5V_Rail_on_Pascal_GPUs. 5V Rail] at VDD, and gets enabled by the PGOOD signal from the Vcore controller.

The controller regulates the 3.3V on the input to 1V on the output. It regulates that voltage through a resistive divider on the FB pin (Figure 2)
## Usage
PEX rail goes directly to the core to power the PCIE logic on it.
## Common problems
### No voltage out
First thing to check is the EN signal which should be 2V+ followed by Vin which should be 3.3V (Figure 2) then VDD which should be 5V. If one of those is missing then check the schematic and follow the signal to find the culprit, it's usually a faulty resistor. Replace the controller if everything else is in order but still no voltage out.
### Short on PEX rail
Generally speaking, a short on the PEX rail is accompanied by a dead core well over 95% of the time. If you have a short on the PEX rail, your efforts should primarily be focused on proving that the core itself is the source of your short. Typically speaking for Nvidia cards, the "PEX" portion of the GPU is in the bottom right corner, and under a thermal camera a shorted PEX rail tends to be noticeably warmer in this location.

If you do not have a thermal camera, a core short can be confirmed by removing the inductor and checking the resistance of each pad to ground. If you have a short on the side that goes to the GPU, then there is a 99% chance the core is dead (this is going to be the case the majority of the time). If the other pad has a short and the core side pad measures fine, then it's most likely a dead component (or more than one) on the line that creates PEX, or the uP1728Q itself.
