---
title: "MacBook Pro A1708 Kills USBC devices repair"
pageid: 183
revid: 1856
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1708_Kills_USBC_devices_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1708_Kills_USBC_devices_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=1856"
last_edited: "2024-01-10T13:29:57Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1708"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1708"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1708 Kills USBC devices repair

## Problem description
This is a dangerous issue that can potentially occur on the A1708 MacBook where the laptop sends more than 5V to connected USB devices, thus killing them. Here's how you could solve this issue.![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Kills USB-C devices

## Solution
Make sure that 20 V is only present on C3101 OR C3201 (PP20V_USBC_XA_VBUS OR PP20V_USBC_XB_VBUS). If A is making 20 V on B, or vice versa, likely need to replace the MOSFETs Q3100 and/or Q3200, since they're letting 20 V through (backwards!) when they're not supposed to.
