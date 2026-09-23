---
title: "EliteBook 850 G5 Freezes when lifted or pressure on bottom"
pageid: 4267
revid: 13843
kind: repair_guide
source: "https://repair.wiki/w/EliteBook_850_G5_Freezes_when_lifted_or_pressure_on_bottom"
history: "https://repair.wiki/index.php?title=EliteBook_850_G5_Freezes_when_lifted_or_pressure_on_bottom&action=history"
permalink: "https://repair.wiki/index.php?oldid=13843"
last_edited: "2026-02-05T16:47:52Z"
contributors:
  - "Cheapskate777"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for EliteBook 850 G5"
infobox:
  Device: "EliteBook 850 G5"
  Affects_parts: "Back plate"
  Needs_equipment: "Phillips Head Screwdriver, Electrical Tape"
  Type: "General"
  Difficulty: "1. Easy"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# EliteBook 850 G5 Freezes when lifted or pressure on bottom

## Problem description
When the laptop is lifted, sitting on an uneven surface, or slight pressure is applied to the back the laptop will either freeze or have a serious kernel error.
## Symptoms
- Screen freezes and user cannot proceed without power cycling the system
- Windows blue screen error message stuck at 0%
- Screen is half black in a checkerboard pattern

## Solution
![Electrical tape added to the back plate where the RAM modules come in contact](images/5/58/EliteBook_850_G5_Modified_Plate.jpg)
The bare metal back plate comes into contact with the RAM modules when pressure is applied to the center of the back of the laptop. When the laptop is plugged into the wall, there is some 60 Hz interference on the back plate (probing scratched areas of the plate reveals measurable voltage). I added a bit of electrical tape to insulate the metal from the RAM. Additionally, I found that flexing the RAM sticks towards the board crashes as well. I added a small dab of hot glue on the middle of the stick to prevent it from bending toward the motherboard. Combining this with [Elitebook 850 G5 Not turning on, 3.2 boot error](Elitebook_850_G5_Not_turning_on%2C_3.2_boot_error.md) I have been able to use two modules of RAM without crashes.

### Diagnostic Steps
Gently press on the edge of a RAM stick while the system is on to see if a crash occurs. If so, add a bit of hot glue to prevent the case flexing the RAM module.

### Repair Steps
1. Remove the 10 screws from the back plate. They are captive screws so they stay on the back plate and don't come out.
1. Set your finger tips into the grove of the hinge on the back of the laptop. Slowly pry the plate back. There are multiple loud clips holding it in place so don't be afraid to use a bit of force.
1. Place 2 strips of electrical tape on the back plate where the RAM makes contact. See the picture for location.
1. Add small dot of hot glue at the center edge of each RAM module so that the sticks do not flex towards the board when pressed. (If you need to remove the sticks in the future, use a heat source to soften the glue)
1. Align the back panel with the hinge placement. Using your palms, press the panel into the back of the laptop by applying pressure around the edges. You will hear several loud snaps as the clips set in place.
1. Screw the 10 captive screws back in place.
