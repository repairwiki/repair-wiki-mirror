---
title: "IPad Pro 12.9 No backlight after screen replacement repair"
pageid: 1388
revid: 13889
kind: repair_guide
source: "https://repair.wiki/w/IPad_Pro_12.9_No_backlight_after_screen_replacement_repair"
history: "https://repair.wiki/index.php?title=IPad_Pro_12.9_No_backlight_after_screen_replacement_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=13889"
last_edited: "2026-02-08T21:11:21Z"
contributors:
  - "Tiago199988"
  - "KevinShort"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPad Pro 12.9 1st Gen"
  - "Repair guides for IPad Pro 12.9 2nd Gen"
  - "Stubs"
infobox:
  Device: "IPad Pro 12.9 1st Gen, IPad Pro 12.9 2nd Gen"
  Affects_parts: "motherboard"
  Needs_equipment: "soldering iron"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPad Pro 12.9 No backlight after screen replacement repair

## Problem description
Fixing an iPad Pro 12.9 that has lost backlight after a screen replacement or device disassembly.
![Example of an iPad with no Backlight](images/7/7a/No_backlight.jpg)

## Symptoms
- Device boots but backlight does not work

## Solution
If there is no backlight after a screen replacement, the screen was most likely connected/disconnected with the battery plugged into the board. This can cause one or both of the backlight filters above one of the display connectors to blow. Replacement of these components will often resolve backlight issues, bellow is a guide on diagnosing the backlight circuit.

## Diagnostic Steps
The first step is check if both backlight filter are ok, with your multimeter in continuity mode check the filter in the image bellow the must have continuity across.

The backlight filters are the most common issue, these filters are cheap and can be found online easily.

![689x689px](images/0/02/69C658A9-8BBC-4D05-A634-0B34DB0E9736-1806-00000182DF41DB99.jpeg)
If the backlight filters are ok the next thing to check is for shorts on the capacitors related to the backlight circuit these caps are used as decoupling capacitor do only one side of thee is connected to GND with your multimeter in continuity mode place a probe on ground and probe the capacitors you can have both side beeping.

![713x713px](images/0/0e/Caps_to_check.png)

After checking for shorts next thing to check is the Diodes check if they have any physcial damage like in the picture bellow.
![Diode Dead.png](images/d/d1/Diode_Dead.png)

## Repair Steps
The filters can be replaced with "0402 120ohm -1.5A Ferrite" (Reference: MPZ1005S121ETD25) to replace it simply use your hot hair station to desolder the old ones and solder the new one. If you dont have the filters on hand you can remove them and jump them, this is not recomenened because if there is a problem again it will damage the circuit.

The Caps can be replaced from a donor board their exact specs are not know since there is not schematics available for this iPad.

The diodes are the same used on iPad Air 1 / Air 2 / Air 3 / Pro 9.7" / Pro 10.5" / Pro 11" 1st Gen (2018) / Pro 12.9" 1st Gen (2015) / Pro 12.9" 2nd Gen (2017) / iPad 5 (2017) / iPad 6 (2018) so finding the them should not be an issue. Use your hot hair gun to replace them. The diodes have orientation make sure you soldering like it was before.

If everything above is ok then the last thing left to check/replace is the backlight controller IC the backlight controller is the same used on iPad 7 and iPad 9 so finding it is not a problem. The chip is 8566 5AR5 and is also available for same in many suppliers.

## Final Testing
After repairing the backlight circuit make sure the device works well and there is no flickering even at max brightness.
