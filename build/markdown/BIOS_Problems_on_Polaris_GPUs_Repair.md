---
title: "BIOS Problems on Polaris GPUs Repair"
pageid: 415
revid: 903
kind: repair_guide
source: "https://repair.wiki/w/BIOS_Problems_on_Polaris_GPUs_Repair"
history: "https://repair.wiki/index.php?title=BIOS_Problems_on_Polaris_GPUs_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=903"
last_edited: "2023-11-07T20:24:57Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for RX 460"
  - "Repair guides for RX 470"
  - "Repair guides for RX 480"
  - "Repair guides for RX 560"
  - "Repair guides for RX 570"
  - "Repair guides for RX 580"
  - "Repair guides for RX 590"
infobox:
  Device: "RX 460, RX 470, RX 480, RX 560, RX 570, RX 580, RX 590"
  Affects_parts: "BIOS Circuit"
  Needs_equipment: "multimeter, soldering iron, soldering station, oscilloscope."
  Type: "Soldering, Software"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# BIOS Problems on Polaris GPUs Repair

## Problem description
If all hardware components on the card are verified to be in good condition and all required voltages are present, but the computer fails to detect the card, it often indicates a BIOS-related issue.

The BIOS circuit operates as follows: During the initialization process, the GPU core pulls pin 1 (CS) low, which activates the BIOS chip. Subsequently, it reads the information stored in the BIOS, including details such as the card's name and clock settings, by communicating through pin 2 (directly connected to the core) and pin 5 (linked through a 33Ω resistor), as illustrated in figure 2. Once these readings are obtained, they are then transmitted to the computer for identification.

- Different board manufacturers might use different bios chips, however, they have have the same pinout and work in the same principle.*

Markings on the schematic and board could differ from GPU model to another but the circuit is almost always the same. [https://eu.mouser.com/datasheet/2/949/w25q40ew_revj_07182018_sfdp-1489916.pdf Here is a reference BIOS chip datasheet.]

The resistors for pins 1, 2, 5, and 6 are often above the bios chip as individual resistors or in a multi resistor package as shown in figure 1.
![Location of the bios chip on an RX 480 Reference (Figure 1)](images/6/6a/Polaris_bios_on_board.jpg)
![Schematic view of the BIOS circuit. (Figure 2)](images/6/61/Polaris_bios_schematic.jpg)

## Symptoms
- All voltages are present on the card but no output.
- The card does not get recognized by the computer or it gets recognized with Error 43 in device manager
- The card works but unreliably (sometimes works but after power cycling it doesn't work)

## Solution
### No picture
First, make sure the bios chip is receiving power through VDD pin.

Then, with an oscilloscope, probing pin 2 and 5 during initialization tells you whether the core is communicating with the bios or not in the first place, if there is complete silence that means the core is not even trying to talk to the bios(probably faulty core or the card has not reached the initialization point). If there is communication then it's either the bios chip is faulty or the BIOS data either got corrupted somehow or a modded/incompatible bios has been flashed on it. Simply flash the original bios (from TPU BIOS Library or the manufacturer's website) using a SPI/USB adapter. Or If there is no communication then check the resistors between the bios and core.

At this point, if the bios is being read and the bios chip is working and has original content on it but still no picture then you probably have another problem, either a faulty core or memory.
### Error 43
Crypto miners usually flash a custom bios to increase the card's efficiency while mining and when they retire those cards, they sell them as is without changing the bios back to the original one. Custom BIOSes work fine on Linux but Windows throws Error 43.

It is possible to flash the bios through windows directly without an adapter using [https://www.techpowerup.com/download/ati-atiflash/ ATI Flash].
