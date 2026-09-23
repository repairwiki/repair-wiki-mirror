---
title: "PlayStation 5 Single beep from power button every 30 seconds repair"
pageid: 681
revid: 6904
kind: repair_guide
source: "https://repair.wiki/w/PlayStation_5_Single_beep_from_power_button_every_30_seconds_repair"
history: "https://repair.wiki/index.php?title=PlayStation_5_Single_beep_from_power_button_every_30_seconds_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=6904"
last_edited: "2025-05-18T00:21:55Z"
contributors:
  - "ASRepairs"
  - "VCCBoardRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for PlayStation 5"
  - "Stubs"
infobox:
  Device: "PlayStation 5"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# PlayStation 5 Single beep from power button every 30 seconds repair

## Problem description
Diagnosing and fixing an issue where the PS5 PWRBTN beeps once every 30 seconds.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- The PlayStation 5 (PS5) emits a single beep from the PWRBTN approximately every 30 seconds.
- The PS5 may not power on or display any video output.

## Solution
- Check fuse F7002 for continuity. If blown you may need to investigate why it went bad (possible short on nearby 5v-3.3v step down converter)
- Check for shorts on 5v-3.3v step-down converter (TLV62090RGTR) directly opposite F7002 (APU side). The capacitor and IC appear to be common failures
- Check liquid metal for spills on and around the APU, as well as under the foam and gasket ([https://www.youtube.com/watch?v=qdyVjvUjfXo Video]  - Credit TheCod3r)
- Check for shorts around the capacitors at the back of the WiFi/Bluetooth module
- Check for shorts around F7502 and F7003
- [https://youtu.be/esV1bP4T-xI Video] (Credit: TheCod3r)
- Check F7502 for continuity (If no, check caps in that area).
