---
title: "MacBook Pro A1502 2013-2014 USB ports not detecting drives repair"
pageid: 494
revid: 1030
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1502_2013-2014_USB_ports_not_detecting_drives_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1502_2013-2014_USB_ports_not_detecting_drives_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=1030"
last_edited: "2023-11-08T18:08:22Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1502"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1502"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1502 2013-2014 USB ports not detecting drives repair

## Problem description
When the A1502 MacBook Pro is not detecting connected USB devices.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Unable to detect USB devices.

## Solution
For left port on logic board check for 5 V at L4605. If low or non existent check for PP5V_S4 at pins 2 and 3 of U4600. If that VIN is OK check for USB_PWR_EN at pin 4. If that is low try removing U4600 and rechecking USB_PWR_EN. If it comes back up to ≈3.3 V then replace U4600 and recheck for 5 V at L4605. This obviously doesn't cover all possible scenarios but it is one.
