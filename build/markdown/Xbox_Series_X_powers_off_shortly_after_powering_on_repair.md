---
title: "Xbox Series X powers off shortly after powering on repair"
pageid: 1186
revid: 4532
kind: other
source: "https://repair.wiki/w/Xbox_Series_X_powers_off_shortly_after_powering_on_repair"
history: "https://repair.wiki/index.php?title=Xbox_Series_X_powers_off_shortly_after_powering_on_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=4532"
last_edited: "2024-07-30T18:14:34Z"
contributors:
  - "HaileyKitty"
  - "Red.repair"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Xbox Series X"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Xbox Series X powers off shortly after powering on repair

## Problem description
Automatic Shutdown after pressing the power button.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Powers off shortly after powering on
- Automatic Shutdown after pressing the power button.

## Solution
- Shutdown within 3 seconds: Short on 12v power rails.
- Shutdown within 3 seconds but no short on 12v or 5v rail:
  - Possible bad SSD
  - Remove SSD and observe if the system powers off immediately afterword. If the system stays on after removing the SSD, it is possible the SSD is the root cause. You will need to clone the boot partition and write it to a donor SSD. See the SSD guide for more details.
- Shutdown within 10 seconds: Short on APU power rails.

If shorts are found on the rails' capacitors, it is probably a chip surrounding them instead of the capacitors themselves. Try to remove surrounding chip one by one and test if the shorts are still there until you find the faulty chip.

If you just replaced the HDMI port, double check your work and make sure you don't have any pins bridged.

Alternatively: Check location **U82** on the main board for a short (The board that has the HDMI port on it). It is on the backside of the board, on the reverse side of the HDMI port. On then off can occur when replacing HDMI port. The chip in question uses the SOT-23-5 package. It appears STMPS2151STR is the original replacement part for this chip, according to a schematic found online of the series X console. TPS2065DBVR & AP2151D appear to be viable replacements as well. A data sheet for the AP2151D chip to view the pinout is available here: https://www.diodes.com/assets/Datasheets/AP2141D_51D.pdf A repair with the U82 chip being the source of the problems can be found here: https://youtu.be/mGSQIc_11gg?si=h4BeNva2z-8JLlQd&t=1047
