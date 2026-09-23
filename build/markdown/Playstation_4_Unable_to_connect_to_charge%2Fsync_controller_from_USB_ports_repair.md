---
title: "Playstation 4 Unable to connect to charge/sync controller from USB ports repair"
pageid: 839
revid: 6542
kind: repair_guide
source: "https://repair.wiki/w/Playstation_4_Unable_to_connect_to_charge/sync_controller_from_USB_ports_repair"
history: "https://repair.wiki/index.php?title=Playstation_4_Unable_to_connect_to_charge/sync_controller_from_USB_ports_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=6542"
last_edited: "2025-05-12T21:47:57Z"
contributors:
  - "ASRepairs"
  - "VCCBoardRepairs"
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Playstation 4"
  - "Stubs"
infobox:
  Device: "Playstation 4"
  Affects_parts: "motherboard"
  Needs_equipment: "multimeter, soldering iron, hot air station"
  Type: ""
  Difficulty: ""
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Playstation 4 Unable to connect to charge/sync controller from USB ports repair

## Problem description
Controller/other usb devices wont connect over USB normally or in safe mode.
![Cap mentioned and voltage regulator that goes bad](images/1/18/CUH-10xxA_-_SAA-001_-_GL3520.png)

## Symptoms
- Cant charge controllers

- Cant sync controllers

- Cant detect usb drives

## Solution
Check that you have 5V on the USB ports, if you do the issue is most likely on the usb circuit and not the southbridge.

Check that you have 3.3V on the side of the cap that i posted, if you have 0V or the voltage is around 2V the problem is usually on a voltage regulator on the other side of the board.

If you have 2V on the cap that i mentioned one way to make sure that the problem its the regulator is to slowy heating him up and see if the voltage goes up or if you have a controller plugged in see if it starts charging. If you see the controller light up or the voltage going up replace the regulator. This is a common problem with this regulator.
