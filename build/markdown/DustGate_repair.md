---
title: "DustGate repair"
pageid: 109
revid: 3809
kind: repair_guide
source: "https://repair.wiki/w/DustGate_repair"
history: "https://repair.wiki/index.php?title=DustGate_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3809"
last_edited: "2024-05-09T10:12:07Z"
contributors:
  - "ASRepairs"
  - "Inwerp"
anonymous_edits: 0
categories:
  - "Apple Laptops"
  - "Missing device page"
  - "Repair guide"
  - "Repair guides for Apple Laptops"
  - "Repair guides for MacBook Air Retina TBT"
  - "Repair guides for MacBook Pro Retina TBT"
  - "Stubs"
infobox:
  Device: "MacBook Pro Retina TBT, MacBook Air Retina TBT, Apple Laptops"
  Affects_parts: "Display assembly"
  Needs_equipment: "soldering iron, replacement glue stripes, replacement LCD Flex cable, 0.02MM solder wire, heating mat"
  Type: "Soldering"
  Difficulty: "4. Specialist"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# DustGate repair

## Problem description
dust pinches hole through flex data cable between Tcon and LCD. this causes different types of malfunction, mostly with 6 even vertical bars (each corresponds image block of the screen).
![typical dustgate](images/5/50/Dustgate_small_pic.png)

## Symptoms
- 6 pink vertical bars on the screen, might change or flicker with different lid angle
- black screen with backlight only (rare, in most cases that would be a cracked screen edge)
The main symptom is the bar pattern. horizontal-lines are caused by damaged LCD / Traces on glass.

## Solution
Confirm the issue with a different screen or external monitor, then refer to the (upcoming) Dustgate Repair page.

To repair this issue, you must either repair a broken trace (remove the logoboard and cable fixture to access the edge part of the cable) or replace both cables. If the cable looks good, inspect the LCD under the logoboard for broken or corroded traces between the orange cable and image decoders on the glass.

All cables have the same pinout; however, 15 and 16-inch ones have a longer grounding pin. Cables are very prone to break, so do not bend them near the soldering area and put UV glue on the other side, just like it was done in manufacturing.

After flex replacement, it is normal to have a flickering screen for 10-20 hours of display operation. The suspected reason is a display synchronization problem due to slightly different impedance in a new cable/confused MCU due to a broken trace in the cable. It goes away by itself, also happens after TCON firmware reflashing.

This type of repair requires lots of practice and advanced repair skills to perform.

Here is instructional video of this repair:
<youtube>spyA05eNN_E</youtube>
