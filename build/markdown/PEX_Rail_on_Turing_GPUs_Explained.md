---
title: "PEX Rail on Turing GPUs Explained"
pageid: 452
revid: 953
kind: explanatory_guide
source: "https://repair.wiki/w/PEX_Rail_on_Turing_GPUs_Explained"
history: "https://repair.wiki/index.php?title=PEX_Rail_on_Turing_GPUs_Explained&action=history"
permalink: "https://repair.wiki/index.php?oldid=953"
last_edited: "2023-11-07T22:10:24Z"
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

# PEX Rail on Turing GPUs Explained

PEX minor voltage rail (PEX VDD) on Turing series of GPUs explained from a repair perspective.

## The Controller Circuit
![PEX rail circuit location on an RTX 2080 Reference. (Figure 1)](images/3/3f/2080_pex_on_board.png)
![Schematic view of the PEX rail with GS9216. (Figure 2)](images/3/3d/2080_pex_GS9216_schematic.png)
![Schematic view of the PEX rail with NB617. (Figure 3)](images/e/e2/2080_pex_mp_schematic.png)
![Schematic view of the EN signal for PEX controller. (Figure 4)](images/3/3d/2080_pex_en.png)
PEX is created by a variety of ICs depending on the card manufacturer but most commonly you'll find a [https://www.monolithicpower.com/en/documentview/productdocument/index/version/2/document_type/Datasheet/lang/en/sku/NB671LB/ NB617LB] or a [http://www.gstekic.com/pdf/GS9216.pdf GS9216].

In the case of GS9216, VCC comes from the [5V rail](5V_Rail_on_Turing_GPUs_Explained.md) through 2.2 ohm resistor usually.

In the case of NB617, VCC comes from the IC itself. However, that is created from the Vin voltage which is 12V_F

Enabling this controller is a logic AND gate whose inputs are the EN and PGOOD of the [VCore](VCore_Rail_on_Turing_GPUs_Explained.md) controller.

PGOOD from this rail can be used to enable NVLINK along with PGOOD from [VCore](VCore_Rail_on_Turing_GPUs_Explained.md).

Markings on the schematic and board could differ from GPU model to another but the circuit is almost always the same.
## Usage
PEX rail goes directly to the core to power the PCIE logic on it.
## Common problems
### No PEX voltage
First thing to check is the EN signal which should be 2V+ followed by Vin/VCC. If one of those is missing then check the schematic and follow the signal to find the culprit, it's usually a faulty resistor. Replace the controller if everything else is in order but still no voltage out.
### Short on PEX rail
Generally speaking, a short on the PEX rail is accompanied by a dead core well over 95% of the time. If you have a short on the PEX rail, your efforts should primarily be focused on proving that the core itself is the source of your short. Typically speaking for Nvidia cards, the "PEX" portion of the GPU is in the bottom right corner, and under a thermal camera a shorted PEX rail tends to be noticeably warmer in this location.

If you do not have a thermal camera, a core short can be confirmed by removing the inductor and checking the resistance of each pad to ground. If you have a short on the side that goes to the GPU, then there is a 99% chance the core is dead (this is going to be the case the majority of the time). If the other pad has a short and the core side pad measures fine, then it's most likely a dead component (or more than one) on the line that creates PEX, or the controller itself.
