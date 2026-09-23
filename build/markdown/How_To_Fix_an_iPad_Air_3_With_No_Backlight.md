---
title: "How To Fix an iPad Air 3 With No Backlight"
pageid: 243
revid: 673
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_an_iPad_Air_3_With_No_Backlight"
history: "https://repair.wiki/index.php?title=How_To_Fix_an_iPad_Air_3_With_No_Backlight&action=history"
permalink: "https://repair.wiki/index.php?oldid=673"
last_edited: "2023-11-05T16:41:00Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPad Air 3"
infobox:
  Device: "iPad Air 3"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix an iPad Air 3 With No Backlight

## Problem description
When an iPad Air 3 comes in for a screen repair, then ends up with no backlight, then maybe the backlight circuit has damage. It usually happens due to the battery not being disconnected while attempting to plug in the screen. You will see the image on the screen but very dim and you will hear all the noises coming from it, but difficult to see the image.
![(Figure 1) - iPad Air 3 Charging with No Backlight](images/7/7a/Ipadair3backlight.jpg)
![(Figure 2) - iPad Air 3 Backlight Diode is cracked & likely part of the cause of no backlight](images/5/53/Air3_diode.jpg)

## Symptoms
Some symptoms include

- Turns on, charges and makes noise, but the screen is dim (Figure 1)
- iPad was working before the screen repair, but now doesn't work after.
- No backlight even after putting back the original screen
- Screen brightness doesn't work

## Solution
### Diagnostic Steps
- Test with known good parts
- Test with the original screen
- If still no backlight, do a visual inspection of the board.
- Look for blown diodes
- (Figure 2) (Figure 2) - iPad Air 3 Backlight Diode is cracked & likely part of the cause of no backlight
  - Diode mode across the diode, with red probe on one leg, black probe on the other.
    - A known good diode will give OL in one direction & some reading in the other direction
    - If you get continuity across the diode, then it's likely bad
- Diode Mode the display connectors, checking for any shorts or open line

### Repair Steps
- ![(Figure 3) - iPad Air 3 Backlight filters that need to be replaced, even if the readings are good across them.](images/2/2d/Air_3_backlight_filters.jpg)![iPad Air 3 fixed, after replacing 2 diodes & 3 backlight filters](images/0/06/Air3_working.jpg)If you find blown backlight diodes, replace them.
  - Make sure you put in the correct orientation
  - Most iPad diodes are compatible. So you can grab from almost any donor board
- If still no backlight, consider replacing all 3 backlight filters next to one of the connectors
  - Refer to Figure 3 (Figure 3) - iPad Air 3 Backlight filters that need to be replaced, even if the readings are good across them.
  - Replace the filters, even if you get good readings across them.
