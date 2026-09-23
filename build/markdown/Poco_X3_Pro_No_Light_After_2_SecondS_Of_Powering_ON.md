---
title: "Poco X3 Pro No Light After 2 SecondS Of Powering ON"
pageid: 5725
revid: 9021
kind: repair_guide
source: "https://repair.wiki/w/Poco_X3_Pro_No_Light_After_2_SecondS_Of_Powering_ON"
history: "https://repair.wiki/index.php?title=Poco_X3_Pro_No_Light_After_2_SecondS_Of_Powering_ON&action=history"
permalink: "https://repair.wiki/index.php?oldid=9021"
last_edited: "2025-07-26T00:57:07Z"
contributors:
  - "Ajimalg82"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Poco X3 Pro"
  - "Stubs"
infobox:
  Device: "Poco X3 Pro"
  Affects_parts: "Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering, Teardown, BGA"
  Difficulty: "4. Specialist"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Poco X3 Pro No Light After 2 SecondS Of Powering ON

## Problem description
When you turn on the device you will see the "POCO" booting logo for the first 1-2 seconds and after that the screen goes black
## Symptoms
- When the device is booted shows "POCO" logo and after 1-2 seconds screen goes blank
![Light on](images/a/a4/Full_light.png)
- Graphics are still hardly visible (with external source of light)
![No Light, only graphics](images/3/34/Low_light.png)
- Light section turns off
- Phone boots up normally
- High Diode value on the Display_CABC, the diode value on this should be ~ 0.610v
![CABC DISPLAY](images/b/b7/CABC_DISPLAY.png)

If you have all the symptoms mentioned above then proceed to the repair steps.

## Solution
This problem occurs due to a missing CABC(pwm) line, this controls the brightness supplied to the display panel. Usually this track gets damaged from inside so the best way to repair it is to make a jumper from under the power ic to the display connector.

- Make sure the Diode Value on this pin is High or OL

- Remove the Power IC

![PMIC](images/1/16/PMIC.png)

- Take a jumper from under the pmic (exact pad shown in the picture) and make a jumper to the display connector (exact pad shown in the picture)

![CABC UNDER PMIC](images/3/33/CABC_UNDER_PMIC.png)
![CABC DISPLAY](images/b/b7/CABC_DISPLAY.png)

- Reinstall the power ic and test.
