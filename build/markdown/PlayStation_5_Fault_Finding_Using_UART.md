---
title: "PlayStation 5 Fault Finding Using UART"
pageid: 4075
revid: 12511
kind: repair_guide
source: "https://repair.wiki/w/PlayStation_5_Fault_Finding_Using_UART"
history: "https://repair.wiki/index.php?title=PlayStation_5_Fault_Finding_Using_UART&action=history"
permalink: "https://repair.wiki/index.php?oldid=12511"
last_edited: "2025-11-02T15:51:52Z"
contributors:
  - "VCCBoardRepairs"
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for PlayStation 5"
  - "Repair guides for PlayStation 5 Pro"
  - "Repair guides for PlayStation 5 Slim"
  - "Stubs"
infobox:
  Device: "PlayStation 5,PlayStation 5 Slim, PlayStation 5 Pro"
  Difficulty: "2. Medium"
  Affects_parts: "Motherboard"
  Needs_equipment: "Soldering Iron, USB-TTL Device"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# PlayStation 5 Fault Finding Using UART

## Introduction
The Southbridge when detecting a problem with a component on the motherboard creates a Error Log.

Using UART to communicate with the console we can request the EMC (Southbridge) to show us the Error logs stored in the console.

These errors can then help us identifying what's wrong with the console.

Unlike the PS4 the EMC UART is already enabled by default (Thx Sony).
![Example of a USB-TTL Device](images/5/58/USB-TTL_Device.jpg)

## Required tools
In order to connect to the PS5 you will need a USB-TTL device doesn't really matter which one,

you will also need a few pieces of wires to connect the device to the console.

You will need a soldering iron.

## Connecting the USB-TTL to the console
In order to connect the PS5 to your device you will need to solder 3 wires to the motherboard RX/TX and GND.

Bellow are the location of the points where we need to solder our wires, the locations vary from board to board.
![PS5 UART Connections](images/c/c3/PS5_UART_conections.png)

Follow the image above solder your 3 wires to the test pads and connect them like the image above.

Remember RX goes to TX and TX to RX.

### Connecting the console to the PC
In order to pull the errors from the console we will need a program to communicate with the console, in this guide we will use Console Service Tool [https://consoleservicetool.com/]

Download and install the software above.

Connect your USB-TTL device to the computer, plug in the power cable of the console but dont turn it on.

Open Console Service tool, click on Sony and then Playstation 5.

Select the your TTL device and click on Run.

You Should get an output like this:
![PS5 Read Error Logs Example Output](images/b/b6/Example_output.jpg)
### What to do with the Codes?
Unfortunately Sony doesn't tell us what every error means, but the repair community as managed to associate many errors with symptoms.

If you get and Error that doesnt have a description look around in other databases for example:

UartCodes.com [https://uartcodes.com/]
