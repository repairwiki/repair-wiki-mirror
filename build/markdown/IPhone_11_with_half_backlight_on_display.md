---
title: "IPhone 11 with half backlight on display"
pageid: 4226
revid: 7226
kind: repair_guide
source: "https://repair.wiki/w/IPhone_11_with_half_backlight_on_display"
history: "https://repair.wiki/index.php?title=IPhone_11_with_half_backlight_on_display&action=history"
permalink: "https://repair.wiki/index.php?oldid=7226"
last_edited: "2025-05-31T14:29:37Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 11"
  - "Stubs"
infobox:
  Device: "iPhone 11"
  Affects_parts: "Motherboard"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope, Multimeter, Thermal Camera"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 11 with half backlight on display

## Problem description
The device turns on and works but there is a dark spot on one of the bottom corners.
![Example of issue iPhone 11 with a dark spot on the left corner](images/3/35/Iphone_11_half_backlight.jpg)

## Symptoms
- There is a dark spot on the bottom left side of the screen
- There is a dark spot on the bottom right side of the screen

### Diagnostic Steps
The first step is to try to swap parts before assuming there is a problem with the motherboard, so start by trying a new display.

If a new display doesn't fix the issue the next step is to diagnose the motherboard.

Why this issue even happens in the first place? Well, because on the iPhone 11 motherboard there are actually 2 backlight circuits for the display.

Start by taking diode readings of the LCD FPC especially the backlight lines and compare with the image below. If a line that should have 0.500 measures 0.000, you know there is a short. If it measures OL or nothing at all, it means that the circuit is open.

![Image FPC Diode readings](images/0/0e/Iphone_11_display_fpc.jpg)
After taking diode readings of the FPC, you will probably already find the line that is faulty, use a program like ZXW to trace where it goes.

The backlight circuits are located under a shield on the top board, so if you're skilled enough, you may not need to split the boards.

As we said before, there are 2 backlight circuits, so if you have a dark spot on the left side of the screen, you should focus your attention there.

![iPhone 11 Backlight Circuits](images/b/b1/Iphone_11_backlight_circuit.jpg)
The most common issue is for the output resistor to be blown, if you already took diode measurements of the FPC you saw that.
![iPhone 11 Backlight Circuit Output Resistors Location](images/7/78/Image.jpg)
A common issue is also a short on PP_DISPLAY_BL12_ANODE or PP_DISPLAY_BL34_ANODE, a short on these lines can destroy the entire circuit. Coils, backlight IC, Caps, and diodes.
![iPhone 11 Blown Backlight Circuit](images/a/a2/Blow_circuit.jpg)
Here is also a schematic of how one IC works in detail.
![iPhone 11 Backlight Circuit Schematic](images/9/90/IPhone_11_Backlight_Circuit_Schematic.png)

### Repair Steps
Replacing the output resistors is easy, find them on a donor board or use any with 0.000 ohm resistance and foot size of 0201.

The backlight IC U5650 or U5660 is an LM3539A1 and can be easily found.

If you have a short on, for example, a capacitor PP_DISPLAY_BL12_ANODE or PP_DISPLAY_BL34_ANODE, it is recommended to remake that circuit.
