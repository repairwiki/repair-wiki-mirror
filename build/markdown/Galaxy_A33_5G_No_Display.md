---
title: "Galaxy A33 5G No Display"
pageid: 9573
revid: 13818
kind: repair_guide
source: "https://repair.wiki/w/Galaxy_A33_5G_No_Display"
history: "https://repair.wiki/index.php?title=Galaxy_A33_5G_No_Display&action=history"
permalink: "https://repair.wiki/index.php?oldid=13818"
last_edited: "2026-02-02T01:05:19Z"
contributors:
  - "Ajimalg82"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Galaxy A33 5G"
  - "Stubs"
infobox:
  Device: "Galaxy A33 5G"
  Affects_parts: "Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering, Teardown, BGA"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Galaxy A33 5G No Display

## Problem description
Galaxy A33 screen does not respond at all. Displays no image, but there is a touch input on the entire panel. Replacing the screen does not fix the issue.

## Symptoms
- No display(graphics) on screen
- Phone boots normally
- Touchscreen works
- Charges normally

## Solution
The problem is due to a missing VDD_LCD_ELAVDD_7P6 signal.

### Repair Steps
![Diode Value](images/b/ba/DIODE_VALUE_main_fpc_galaxy_a33_5g.png)

- Check GR on the connector (you will get a missing GR on a following pin)![BURNED PIN](images/d/d1/BURNED_PIN_galaxy_a33_5g.png)
- Check GR on the Capacitor where the area is burned, if GR is ok then proceed to do the jumper like in the following picture![JUMPER](images/f/f5/JUMPER_samsung_galaxy_a33_5g.png)
- Test the display if it works
- If everything seems fine cover the jumper with UV oil.
