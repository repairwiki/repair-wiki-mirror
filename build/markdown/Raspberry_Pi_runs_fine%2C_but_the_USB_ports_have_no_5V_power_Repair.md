---
title: "Raspberry Pi runs fine, but the USB ports have no 5V power Repair"
pageid: 979
revid: 2332
kind: repair_guide
source: "https://repair.wiki/w/Raspberry_Pi_runs_fine,_but_the_USB_ports_have_no_5V_power_Repair"
history: "https://repair.wiki/index.php?title=Raspberry_Pi_runs_fine,_but_the_USB_ports_have_no_5V_power_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=2332"
last_edited: "2024-01-13T20:54:36Z"
contributors:
  - "ASRepairs"
  - "HaileyKitty"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Raspberry Pi"
  - "Stubs"
infobox:
  Device: "Raspberry Pi"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Raspberry Pi runs fine, but the USB ports have no 5V power Repair

## Problem description
Raspberry Pi runs fine, but the USB ports have no 5V power.

- Pi **1** (B+ only)
- Pi **2** (all)
- Pi **3** (B only)

![The ferrite beads next to the LAN9514 chip](images/1/17/LAN9514_marked.jpg)

## Symptoms
- Raspberry Pi runs fine.
- USB ports have no 5V power.

## Solution
his problem may be caused by faulty ferrite beads next to the LAN9514 chip.

Remove all power from the Pi and measure the resistance of the ferrite beads (especially the one highlighted red in the image). The resistance should be below 1 Ohm.

Broken ferrite beads need to be replaced. The part number of the original part is `BLM18AG601`.

If the original part is not available, the ferrite bead next to the WiFi chip on a Raspberry Pi Zero W can be used as a replacement. It should also be possible to bridge broken ferrite beads with a wire, although doing so will increase electromagnetic interference.

Also see [LAN9514 (Raspberry Pi)](Raspberry_Pi_LAN9514.md).
