---
title: "IPad Pro 11in 1st Gen Not Recognized by PC in Recovery Mode or Charging Issues"
pageid: 5707
revid: 9011
kind: repair_guide
source: "https://repair.wiki/w/IPad_Pro_11in_1st_Gen_Not_Recognized_by_PC_in_Recovery_Mode_or_Charging_Issues"
history: "https://repair.wiki/index.php?title=IPad_Pro_11in_1st_Gen_Not_Recognized_by_PC_in_Recovery_Mode_or_Charging_Issues&action=history"
permalink: "https://repair.wiki/index.php?oldid=9011"
last_edited: "2025-07-25T19:03:21Z"
contributors:
  - "Samhext"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPad Pro 11in 1st Gen"
  - "Stubs"
infobox:
  Device: "IPad Pro 11in 1st Gen"
  Affects_parts: "Charge port, Motherboard"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPad Pro 11in 1st Gen Not Recognized by PC in Recovery Mode or Charging Issues

## Problem description
iPad Pro 11in 1st Gen will have strange charging issues and not connect to a PC with itunes or 3utools even in recovery or DFU mode
![451x451px](images/7/77/Recovery-mode-ipad-pro-face-id.png)

## Symptoms
- iPad will not connect to PC with itunes or 3utools even in recovery or DFU mode
- Charging issues, including not charging at all, only charging on USB PD charger capable of 15v and not on USB-A 5v charger or the other way around

### Diagnostic Steps
For this issue there's usually three points of failure, if you are having strictly no charging issues but ipad will connect to PC in recovery there would be additional parts of the board that could cause no charging however the three points of failure we talk about in this guide are also the most common issues for strictly no charging.

1. Charge port
1. * This will be the most common point of failure
1. * The charge port on this model is not soldered to the board and can be easily swapped with a known good port to rule it out.
1. ** Make sure you use a known good port or OEM/Premium parts to test with.  Aftermarket charging ports can have issues themselves.  If you don't have a known good port to test with, try testing with several ports.![Location of CD3215 IC on iPad Pro 11" 1st Gen](images/0/01/Screenshot_From_2025-07-25_11-38-40.png)
1. CD3215 IC
1. * The CD3215 IC mainly handles charging from USB-PD chargers.
1. * If this IC fails you will potentially be able to charge via a 5v USB-A charger but it will not negotiate to charge at 15v through a USB-C PD charger.
1. * To check this IC, probe the capacitors around the chip with your multimeter in diode mode with your red probe on ground and black probe testing each side of the capacitor to make sure none of the caps are shorted to ground on both sides.
1. * If you do find a shorted capacitor around the CD3215 IC, proceed down to the repair steps for fixing the CD3215 below
1. ![Location of Tristar 610A3C on iPad Pro 11" 1st Gen](images/2/2f/Screenshot_From_2025-07-25_11-38-12.png)Tristar 610A3C IC
1. * This model as well as the iPad pro 12.9 3rd gen use a special Tristar "A3C" model that is not backwards compatible with any other Tristars.
1. * The tristar will mainly handle 5v USB-A charging rather than 15v USB-C PD charging.
1. * This IC is hidden underneath a part of the shield above the screen FPC connectors in the middle of the board.  You will need to remove enough of the shield to properly test and/or replace the tristar.  It's best to use a grinding tool, or snips in order to remove enough of the shield for access to the tristar
1. * Just like we did with the CD3215 diagnostics, probe around the tristar IC for shorted capacitors with your multimeter.
1. * The caps around this IC will not always become shorted when the IC fails, so if you have already tested with a known good charging port, have found no shorts around the CD3215, can charge with a USB-C PD charger but only at 15v and cannot charge with a 5v charger then the tristar is more than likely the culprit and you can proceed down to the repair steps for the Tristar 610A3C below

### Repair Steps
1. Charge port
1. * This will be the most straightforward repair and the most common.
1. * Since the port is not soldered to the board, all you have to do is pull the old port off and replace it with the new one
1. CD3215 IC
1. * If you've found one or more shorted capacitors around the CD3215 IC then you will first want to rule out the capacitor itself from being the problem rather than just continuing on to replacing the IC
1. * Use a DC power supply set to a low voltage like 1v/1a and place your black probe on ground and your red probe on the side of the capacitor that is not connected to ground.  Then use a thermal camera or freeze spray to determine if it is one of the capacitors on the shorted line that heats up first or if it's the CD3215 IC
1. * If a capacitor heats up first, then you will need to remove it with a blade or pry tool, it should be loose and easy to break off, then using your multimeter in diode mode, confirm that the short is no longer present.
1. ** Most capacitors will be smoothing caps which have many other caps connected to the same line and as long as there are other caps on the same line you don't need to replace the shorted cap since the other ones can pick up the slack
1. * If your CD3215 is shorted then your will need to replace it.  They can be purchased from many distributors or pulled from a working ipad or macbook  donor board with the same IC.
1. * After replacing the CD3215, test to make sure the short is no longer present, or that the ipad is able to negotiate 15v charging from a USB-C PD charger capable of 15v.  Also test to make sure the ipad is again able to be recognized by itunes or 3utools
1. Tristar 610A3C
1. * If you do happen to find a shorted capacitor around the tristar then you will need to go through the same steps above that were used for the CD3215, by injecting a small voltage into the line and using freeze spray or a thermal camera to see if a faulty cap heats up first or if the Tristar does and ultimately removing the shorted cap or replacing the tristar.
1. * If you didn't find a shorted cap but are still suspecting the tristar is the issue then you will need to replace it.  Again, most distributors will have this IC or you can pull it from an iPad pro 11" 1st gen or iPad pro 12.9" 3rd gen donor board.
1. * After replacing the Tristar 610A3C, test to make sure the short is no longer present if you had one, or that the ipad is able to charge at 5v using a USB-A charger.  Also test to make sure that the iPad is again recognized by itunes or 3utools especially withing recovery or DFU mode
