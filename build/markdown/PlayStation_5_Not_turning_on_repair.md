---
title: "PlayStation 5 Not turning on repair"
pageid: 680
revid: 6873
kind: repair_guide
source: "https://repair.wiki/w/PlayStation_5_Not_turning_on_repair"
history: "https://repair.wiki/index.php?title=PlayStation_5_Not_turning_on_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=6873"
last_edited: "2025-05-16T23:05:49Z"
contributors:
  - "ASRepairs"
  - "Tiago199988"
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

# PlayStation 5 Not turning on repair

## Problem description
Diagnosing and fixing issues related to "No power" on a PS5
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Not turning on

## Solution
- Check power supply is outputting 12v at PSU Connector on board
- Check for shorts around rear of southbridge IC CXD90061GG. This may indicate the IC itself is to blame. Replacements are available and they're not married.
- Plug your bench power supply into the 12v input pins. If you have no 300ma boot sequence, remove BIOS IC for 10-20 minutes completely from the board, re-solder and retry. If still no change reprogram BIOS with a working digital edition copy of the BIOS (this will remove the ability to use a BDROM on disc editions)
- [https://youtu.be/jphoO6dQ4oo Video] (Credit: TheCod3r)
