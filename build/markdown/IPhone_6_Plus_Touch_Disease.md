---
title: "IPhone 6 Plus Touch Disease"
pageid: 4727
revid: 7811
kind: repair_guide
source: "https://repair.wiki/w/IPhone_6_Plus_Touch_Disease"
history: "https://repair.wiki/index.php?title=IPhone_6_Plus_Touch_Disease&action=history"
permalink: "https://repair.wiki/index.php?oldid=7811"
last_edited: "2025-06-19T13:27:46Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone 6 Plus"
  - "Stubs"
infobox:
  Device: "IPhone 6 Plus"
  Affects_parts: "Motherboard"
  Needs_equipment: "Soldering Iron, Hot-Air Station, Microscope, Multimeter"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 6 Plus Touch Disease

## Problem description
The iPhone turns on but touch doesn't work or its intermittent
![iPhone 6 Plus Touch Disease!](images/9/92/IPhone_6_Plus_Touch_Disease.jpg)

## Symptoms
- Touch does not work
- Touch is intermittent
- Touch doesn't work and some weird lines show up in the top part of the screen when you flex the phone

## Solution
Usually on phones with no touch we start by taking diode measurements of the FPC connectors on the iPhone 6 Plus we can skip that. This issue is old and it was really common, at some point Apple was even involved in a lawsuit over this issue

This issue is caused by a disconection of the black touch IC U2402.

### Repair Steps
To fix this issue we will need to remove the U2402 and run a small jumper wire to avoid the problem coming back.

The first step is to take out the motherboard out.

If this is your first time doing this repair I recommend that you remove the underfill from these components. Since we will work on the backside of them they may disconnect, if these components disconnect it may cause problems like the front camera not working, the earpiece not working.
![Where to remove the underfill](images/d/da/Where_to_remove_the_underfill.png)
To remove this underfill it doesnt take much heat i recomend using your heatgun and a 007 blade like the image bellow.
![007 Blade](images/4/4b/007_Blade.png)
After removing the underfill we can proced to remove the touch IC.

The touch ic is located on the back side of the motherboard near the WIFI IC.
![U2402 Location](images/a/a2/U2402_Location.png)

Use your heat gun to desolder the chip be careful to not use excessive heat since the CPU is on the other side and excessive heat may cause it to disconnect.

After removing the IC add some low-melt solder with your soldering iron to the pads on the motherboard to make it easier to clean.

Clean the solder from the pads on the motherboard.

After cleaning the pads, check for any ripped pads, you may have one missing that is common to break the "M1" pad.

Even if the pad is not missing i recomend to make the jump anyway since it is common for the pad to brake and issue will come back.
![M1 Jumper](images/9/95/M1_Jumper.png)
After doing the jump, you can reball the old chip and solder it back on the board or you can buy a pre-balled one.

### Final Testing
Make sure touch is working properly, gently flex the phone and check if it's working well, no line appear on the screen.

Test every function of the device, it is common to have issues with the front camera after this repair due to those components mentioned before.
