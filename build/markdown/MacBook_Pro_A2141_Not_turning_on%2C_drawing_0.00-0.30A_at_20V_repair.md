---
title: "MacBook Pro A2141 Not turning on, drawing 0.00-0.30A at 20V repair"
pageid: 111
revid: 508
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A2141_Not_turning_on,_drawing_0.00-0.30A_at_20V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A2141_Not_turning_on,_drawing_0.00-0.30A_at_20V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=508"
last_edited: "2023-10-29T15:27:26Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A2141"
  - "Stubs"
infobox:
  Device: "MacBook Pro A2141"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering, Software"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A2141 Not turning on, drawing 0.00-0.30A at 20V repair

## Problem description
No Power on, 20v and ~0.00-0.3A as measured on the USB-C amp meter, with power cycling on the 820-01700 logic board.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- PPBUS_G3H at 12.5 V
- MacBook not turning on
- Power cycling 0.00 - 0.30 A at 20V as measured by USBC meter

## Solution
Found C9586 for PP2V5_NAND short

This spot on the board is VERY susceptible to corrosion with no liquid damage. It is placed in the path of incoming cooling air, so dirt and dust build up in this spot causing moisture to be retained, resulting in corrosion. Recommend a conformal coat on this area once repair is done. After removing the short and verifying PP2V5 is present you may find the no power is almost the same, but now taking 20 V, 0–20 mA. If the rest of the board passes visual inspection, and no other shorts are suspected, the next step is to DFU revive.

(***CAUTION*** DFU Revive must never be mixed up with DFU Restore, DFU revive keeps data on the drive, DFU Restore erases all data)

DFU Revive: Place the logic board back into the machine connecting everything but the battery cable (you can screw the battery connector on just leave the cable disconnected, in a properly functioning battery disconnecting the cable isolates the battery from the board without the need to unscrew the connector)

On a working machine load "Apple Configurator 2" and have an Apple USBC charging cable ready. On your no power machine locate SWK003, this is a "no stuff" button for SOC_FORCE_DFU, it is next to the T2 chip below the keyboard connector. The process is you will short theses pads while connecting the power. You can solder a wire between them or use tweezers or a screwdriver. Now plug the charging cable between your machine running "Apple Configurator 2" and the "master" port on the no power machine (the left side closest to the trackpad). The middle of the "Apple Configurator 2" window should show a large box with the letters DFU in. Right click on the box and choose "advanced", and then "revive device". After some time the no power machine should start taking normal current and turn on. The box in "Apple Configurator 2" should change to a lock symbol.

Note: If the DFU logo comes up after shorting the pads and then goes off again in a loop, plug in a USB-C power adapter AS WELL as a USB-C cable connecting to the other Mac. This is generally needed if the battery is completely flat.
