---
title: "Raspberry Pi runs fine, but there is no picture when using HDMI Repair"
pageid: 988
revid: 2339
kind: other
source: "https://repair.wiki/w/Raspberry_Pi_runs_fine,_but_there_is_no_picture_when_using_HDMI_Repair"
history: "https://repair.wiki/index.php?title=Raspberry_Pi_runs_fine,_but_there_is_no_picture_when_using_HDMI_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=2339"
last_edited: "2024-01-13T21:15:50Z"
contributors:
  - "HaileyKitty"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Raspberry Pi"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Raspberry Pi runs fine, but there is no picture when using HDMI Repair

## Problem description
Raspberry Pi runs fine, but there is no picture when using the HDMI port.
![Pi 3B HDMI Circuit](images/0/0c/Pi3B_HDMI_Circuit.jpg)

## Symptoms
- No picture when using the HDMI port.

## Solution
- Test the internal flyback diodes of transistors `Q2` and `Q5` with a multimeter. The voltage drop should be in the range of 500 to 700mV. If there is a short (0V), the respective transistor needs to be replaced. Its part number is `DMG1012T`.

- Use the diode testing mode of a multimeter and connect the black lead to GND (e.g. the metal part of the micro-USB socket). Use the red lead to probe the contacts on top of `L4` to `L7` (highlighted pink in the image). There should be no reading. If any value is shown while touching any of the four coils (e.g. 1100mV), the HDMI circuitry inside the CPU is probably broken. This fault cannot be repaired.
