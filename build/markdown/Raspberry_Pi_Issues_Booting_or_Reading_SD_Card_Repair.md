---
title: "Raspberry Pi Issues Booting or Reading SD Card Repair"
pageid: 989
revid: 2341
kind: other
source: "https://repair.wiki/w/Raspberry_Pi_Issues_Booting_or_Reading_SD_Card_Repair"
history: "https://repair.wiki/index.php?title=Raspberry_Pi_Issues_Booting_or_Reading_SD_Card_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=2341"
last_edited: "2024-01-13T21:19:09Z"
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

# Raspberry Pi Issues Booting or Reading SD Card Repair

## Problem description
Raspberry Pi having issues with booting or reading the SD card.

- Pi **4**
- Maybe other models too

![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- The error Failed to open device: 'sdcard' (cmd 371a0010 status 1fff0001) appears in the boot screen.
- The system fails to read data from the SD card.
- The system boots only after a weak bending force is exerted on the PCB.
- The system freezes randomly, or after a weak bending force is exerted on the PCB.

## Solution
- Test the SD card in another Pi to make sure that it's actually working
- Check the condition of the SD card slot. Fix any issues with it, and reflow the solder of the SD card slot.
- Reflow the solder underneath the CPU using hot air at 350°C / 660°F.
