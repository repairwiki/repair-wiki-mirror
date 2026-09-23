---
title: "PlayStation 3 Fault Finding Using UART"
pageid: 5301
revid: 12555
kind: other
source: "https://repair.wiki/w/PlayStation_3_Fault_Finding_Using_UART"
history: "https://repair.wiki/index.php?title=PlayStation_3_Fault_Finding_Using_UART&action=history"
permalink: "https://repair.wiki/index.php?oldid=12555"
last_edited: "2025-11-02T20:59:35Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for PlayStation 3 Super Slim"
  - "Repair guides for Playstation 3 CECH‑L04"
  - "Repair guides for Playstation 3 Slim"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# PlayStation 3 Fault Finding Using UART

## Problem description
The Syscon when detecting a problem with a component on the motherboard creates a Error Log.

Using UART to communicate with the console we can request the Syscon to show us the Error logs stored in the console.

These errors can then help us identifying what's wrong with the console.
![Example of a USB-TTL Device](images/5/58/USB-TTL_Device.jpg)

## Required tools
In order to connect to the PS3 you will need a USB-TTL device doesn't really matter which one.

You will also need a few pieces of wires to connect the device to the console.

You will need a soldering iron.

## Connecting the USB-TTL to the console
In order to connect the PS3 to your device you will need to solder 3 wires to the motherboard RX/TX and GND.

Bellow are the location of the points where we need to solder our wires, the locations vary from board to board.

![Models A-E (COK-00X)](images/5/52/Models_A-E_(COK-00X).jpg)
![Model G (SEM-001).](images/d/de/Model_G_(SEM-001).jpg)
![Models H-K (DIA-00X)](images/3/33/Models_H-K_(DIA-00X).jpg)
![Models L-Q (VER-001)](images/5/5a/Models_L-Q_(VER-001).jpg)
![Model 20xx (DYN-001)](images/c/cb/Model_20xx_(DYN-001).jpg)
![All Super Slim Models](images/6/69/All_SS_Models_(MSX-001,_MPX-001,_NPX-001,_PPX-001,_PQX-001,_RTX-001,_&_REX-001).jpg)
Follow the image above solder your 3 wires to the test pads and connect them like the image above.

  - Remember RX goes to TX and TX to RX.**

### Connecting the console to the PC
In order to pull the errors from the console we will need a program to communicate with the console, in this guide we will use SysconReader [https://github.com/db260179/ps3syscon/tree/master/Windows/SysconReader]

Download and install the software above.

Connect your USB-TTL device to the computer, plug in the power supply of to the console and plug it in but dont turn the console on.

Next open the program and select the COM port where your USB-TTL is connected to.

Then there 2 types of syscon on PS3 Consoles Mullion (CXR) and Sherwood (SW) select the correct one according to the images bellow.

![Mullion Syscons](images/5/54/Mullion_syscons.jpg)

![Sherwood Syscons](images/3/38/Sherwood_syscons.jpg)

After selecting the right type of syscon click on Start.

After a click on AUTH and wait for a green text saying sucess if you get fail multiple times keep trying and if still falling check your wiring.

After AUTH sucess click on Get Error Codes and wait for the process to finish.

Expected output:
![PS3 Syscon expected output](images/4/4e/PS3_Syscon_expected_output.png)

### What to do with the Codes?
Unfortunately Sony doesn't tell us what every error means, but the repair community as managed to associate many errors with symptoms.

The most up to date database of syscon errors is on PS3 Dev Wiki [https://www.psdevwiki.com/ps3/Syscon_Error_Codes]
