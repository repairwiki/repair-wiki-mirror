---
title: "IPhone XR with half backlight on display"
pageid: 4235
revid: 7237
kind: repair_guide
source: "https://repair.wiki/w/IPhone_XR_with_half_backlight_on_display"
history: "https://repair.wiki/index.php?title=IPhone_XR_with_half_backlight_on_display&action=history"
permalink: "https://repair.wiki/index.php?oldid=7237"
last_edited: "2025-05-31T22:16:57Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone XR"
  - "Stubs"
infobox:
  Device: "IPhone XR"
  Affects_parts: "Motherboard"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope, Multimeter"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone XR with half backlight on display

## Problem description
The phone turns on but there is a dark spot in the bottom part of the display.
![Example of iPhone XR with Half Backlight](images/2/20/Iphone_XR_Half_Backlight.jpg)

## Symptoms
- There is a dark spot on the bottom left side of the screen
- There is a dark spot on the bottom right side of the screen

### Diagnostic Steps
The first step is to try to swap parts before assuming there is a problem with the motherboard, so start by trying a new display.

Why this issue even happens in the first place? Well, because on the iPhone XR motherboard there are actually 2 backlight circuits for the display.

Start by taking diode readings of the LCD FPC especially the backlight lines and compare with the image below. If a line that should have 0.500 measures 0.000, you know there is a short. If it measures OL or nothing at all, it means that the circuit is open.

![iPhone XR Display FPC Diode Readings](images/b/b0/Iphone_XR_display_fpc.jpg)

After taking diode readings of the FPC, you may already find the line that is faulty, use a program like ZXW to trace where it goes.

With just the battery connected and with the phone off, these 2 test points should have around 4V.

![iPhone XR backlight test points](images/e/e4/Iphone_XR_backlight_test_points.jpg)

If you don't have any voltage here, it means that there is a problem with the input circuit, probably the coil or the diode, use ZXW to trace where the line goes.

With the phone on and with a screen plugged in, those points should have around 17V and 25V, if you have the same voltage with the phone on, it means the backlight IC is not working, you measure a higher, for example, 7V, it can be a faulty coil on the output.

As we said before, there are 2 backlight circuits, so if you have a dark spot on the left side of the screen, you should focus your attention there.
![IPhone XR Backlight Circuits](images/4/49/IPhone_XR_backlight_circuit.jpg)
Here is the schematic diagram of how the circuit works.
![iPhone XR Backlight Circuit Schematic](images/f/f5/IPhone_XR_Backlight_Circuit_Schematic.png)

### Repair Steps
The backlight IC U5650 or U5660 is an LM3539A1 and can be easily found.

If you have a short on, for example, a capacitor PP_DISPLAY_BL12_ANODE or PP_DISPLAY_BL34_ANODE, it is recommended to remake that circuit.
