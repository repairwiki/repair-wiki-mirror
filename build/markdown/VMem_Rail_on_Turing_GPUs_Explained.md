---
title: "VMem Rail on Turing GPUs Explained"
pageid: 447
revid: 947
kind: other
source: "https://repair.wiki/w/VMem_Rail_on_Turing_GPUs_Explained"
history: "https://repair.wiki/index.php?title=VMem_Rail_on_Turing_GPUs_Explained&action=history"
permalink: "https://repair.wiki/index.php?oldid=947"
last_edited: "2023-11-07T22:05:15Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Explanatory guide"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# VMem Rail on Turing GPUs Explained

VMemory voltage rail (FBVDD) on Turing GPUs explained.

## The controller circuit
![Vmem controller circuit on the RTX 2080 Reference. (Figure 1)](images/8/89/2080_vmem_circuit_on_board.jpg)
![UP9512P pinout and circuit on RTX 2080. (Figure 2)](images/a/a3/2080_vmem_up9512_schematic.png)
![Vmem controller circuit for UP1666q on RTX 2080. (Figure 3)](images/c/c8/2080_up1666q_circuit.jpg)
![Pinout for UP9512S. (Figure 4)](images/0/0c/2080_up9512S_pinout.jpg)
![Pinout for UP9529. (Figure 5)](images/c/cf/2080_up9529_pinout.jpg)
![Enable signal for Vmem on RTX 2080. (Figure 6)](images/8/80/2080_vmem_en.jpg)
on Turing GPUs, the PWM controller responsible for regulating VMem voltage can differ a lot from different board makers but the most common ones used are UP9512P or UP9512S or UP9529 (no public datasheet for them but pinout is available in the schematics below) or [https://pdf1.alldatasheet.com/datasheet-pdf/view/1113871/UPI/UP1666Q.html UP1666Q].

The controller usually gets its power from [5V rail](5V_Rail_on_Turing_GPUs_Explained.md) through a low resistance (0-10Ω) resistor

Enabling this controller is the 1.8V rail through 0Ω resistors then to a logic AND gate as one of the inputs and the other input is the output from an AND gate whose inputs are the EN and PGOOD of the VCore controller.

PGOOD from this controller is not used for anything.

## Usage
The controller regulates the voltage going to power the memory modules and the memory controller on the core itself. Switching 12 V to 1.3-1.5V.

Depending on the model and manufacturer of the board and the components used, the PWM signals either go to the VRMs directly or through a driver first.

## Common problems
### No VMem Voltage
Check if the controller has 5/3.3V on its VCC, and around 3 V on EN. If one of them is missing trace their respective circuits and check for broken, knocked off, or defective components

If EN and VCC are present and still no output, check the VREF pin, it should be 2 V. If not, the controller itself might be the culprit.

And if everything seems fine, probe around the controller for shorted caps or malfunctioning resistors.
### Short on VMem
This is a not a great situation to be in. If you're lucky, a memory module could be shorted, you can check that by injecting 1V to VMem and applying isopropyl alcohol on the memory chips and see if one or more of the memories are heating up, evaporating the alcohol faster than the rest. Otherwise though, if it's not a shorted capacitor somewhere odds are the core itself is shorted.
