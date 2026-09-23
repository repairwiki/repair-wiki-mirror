---
title: "Galaxy A125(Mediatek) No Graphics"
pageid: 4820
revid: 7939
kind: repair_guide
source: "https://repair.wiki/w/Galaxy_A125(Mediatek)_No_Graphics"
history: "https://repair.wiki/index.php?title=Galaxy_A125(Mediatek)_No_Graphics&action=history"
permalink: "https://repair.wiki/index.php?oldid=7939"
last_edited: "2025-06-22T21:10:08Z"
contributors:
  - "Ajimalg82"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Galaxy A12"
  - "Stubs"
infobox:
  Device: "Galaxy A12"
  Affects_parts: "Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering, BGA"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Galaxy A125(Mediatek) No Graphics

## Problem description
The mobile phone turn on normally, vibrates, can hear sounds but cannot see anything on the screen (not to be confused with backlight issue) cannot see anything even with torch.
## Symptoms
- Device turns on normally
- No light and no graphics
- Can hear sounds
- Charging is normal and can be detected on computer

## Solution
There is a assential voltage for graphics that comes from PMIC that gets disconnected after several drops and the solution for this is that you have to make a small jumper to reconnect the disconnected pad in order to have it fully function again.

### Repair Steps
Check Diode value on this pin(if value is OL or high then proceed to the repair steps):
![Diode Value](images/9/9f/Pin-7.png)

- Lift up the PMIC
- Check pad #A17 if its disconnected, if not try to move it and see if it comes off or its lose (shown in picture below)
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/f/f7/Missing_pad.png)
- Make a jumper for the pad no.17 from the nearest component to the pmic (shown in picture below)
![A17 jumper](images/2/28/Jumper_to_make.png)
- Check continuity, if its ok then gently clean the area and apply uv solder mask
- Reball and reinstall the power ic
- Your device should be fully functional again.
