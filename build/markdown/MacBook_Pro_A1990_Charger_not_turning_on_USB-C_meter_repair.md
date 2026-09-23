---
title: "MacBook Pro A1990 Charger not turning on USB-C meter repair"
pageid: 116
revid: 490
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1990_Charger_not_turning_on_USB-C_meter_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1990_Charger_not_turning_on_USB-C_meter_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=490"
last_edited: "2023-10-29T15:26:03Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1990"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1990"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1990 Charger not turning on USB-C meter repair

## Problem description
When charging the A1990 MacBook with a USB-C charger and measuring the input current and voltage with a USB-C meter, the meter does not even turn on at all or 0 current.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- MacBook not turning on.
- All voltages missing.
- Not charging.

## Solution
### Diagnostic Steps
#### Check PP20V_USBC and PPDCIN_G3H resistance
- Measure the resistance between PP20V_USBC and GND with a multimeter on resistance mode
  - if you read less than 50 ohms, you have a short, proceed to "Short on PP20V_USBC or PPDCIN_G3H" repair steps below
- Measure the resistance between PPDCIN_G3H and GND with a multimeter on resistance mode
  - if you read less than 50 ohms, you have a short, proceed to "Short on PP20V_USBC or PPDCIN_G3H" repair steps below

#### Faulty USB-C port
If both rails above are not shorted, it is highly likely that the USB-C port itself is shorted or damaged inside.

### Repair Steps
#### Short on PP20V_USBC or PPDCIN_G3H
[How to find short circuits](How_to_find_short_circuits.md)

- Inject 1V to the shorted rail using a Lab Bench Power Supply.
  - With a thermal camera, identify the source of the short, most likely it is a capacitor
- Replace the shorted component.

#### Shorted USB-C port
Replace the offending port.
