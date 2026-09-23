---
title: "Base Voltage Rails For GPUs Explained"
pageid: 326
revid: 4905
kind: explanatory_guide
source: "https://repair.wiki/w/Base_Voltage_Rails_For_GPUs_Explained"
history: "https://repair.wiki/index.php?title=Base_Voltage_Rails_For_GPUs_Explained&action=history"
permalink: "https://repair.wiki/index.php?oldid=4905"
last_edited: "2024-09-21T22:48:49Z"
contributors:
  - "ASRepairs"
  - "Galkinvv"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for AMD GPUs"
  - "Explanatory guides for Nvidia GPUs"
  - "Missing device page"
infobox:
  Device: "Nvidia GPUs, AMD GPUs"
  Type: "Circuit"
  Difficulty: "1. Easy"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Base Voltage Rails For GPUs Explained

This page explains base voltages on [Desktop Graphics Cards](Desktop_Computers.md). While most cards work in the same principle, some might have different design. This page should be applicable on most consumer GPUs.

  - Base Voltage Rails are the rails that get supplied to the card externally.**

## 12V_BUS and 12V_EXT
On most Nvidia GPUs, the 12V_Bus is used to power the first 2 phases for the Vcore and every other minor rail such as 5V, meaning powering on the card without the external 8-pin connectors will put the card in a bootable state which shows a text saying "please power off the computer and connect the external 8-pin connectors". The 12V_Ext is used to feed the rest of the Vcore phases. On most AMD GPUs however, the card will not turn on at all if the 8-pin connector isn't inserted as it is used as a signal to power on some ICs.
![PCIe slot pinout (Figure 1)](images/d/d6/PCIe_Slot_Pinout.jpg)
![6 and 8 pin PCIe power connector (Figure 2)](images/f/fe/8_and_6_pin_PCI-E_connectors.jpg)
![RX 590 Nitro+ PCB (Figure 3) *From of TechPowerUp*](images/b/b9/RX_590_Nitro+.jpg)
From Figure 1, you can see the card gets its 12V_Bus from first 3 pins from the front and 2nd and 3rd pin from the back, they're all connected together and usually pass through a 0Ohm resistor that acts as a fuse or in some cards an actual fuse before going through the card (Figure 3).

In case of a short, those fuses are the first to go out to protect the card. Sometimes they can malfunction and either have a high resistance where the 12v drops to a lower voltage or simply blow and become open.

Make sure to check both ends of the fuse for a short to ground before replacing, it's usually rare that they blow up for no reason.

The fuses are usually the 10-15Amp variety.

In Figure 2, the 4th pin for the 8-pin PCIe connector is used for detection while for the 6-pin connector, the 5th is used for that purpose. When those detection pins are shorted to GND (i.e. when you connect the connector itself), the card thinks that the connector is plugged in.

## 3.3V_BUS
![GTX 1080 Ref PCB (Figure 4) *From TechPowerUp*](images/0/0f/GTX_1080.jpg)
The 3.3V rail comes only from the PCIe connector, 8th pin from the front, and 9-10th pins from the back. 3.3V is used as the enable voltage for some ICs and as Voltage In for others e.g. the bios chip. The card does not pull a lot of current through this rail so it does not usually come with a fuse, shunt resistor or a coil but sometimes it does as shown in Figure 4.
