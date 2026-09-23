---
title: "MacBook Air A2179 Not turning on, either 5V or 20V on USBC but with low current draw repair"
pageid: 87
revid: 473
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Air_A2179_Not_turning_on,_either_5V_or_20V_on_USBC_but_with_low_current_draw_repair"
history: "https://repair.wiki/index.php?title=MacBook_Air_A2179_Not_turning_on,_either_5V_or_20V_on_USBC_but_with_low_current_draw_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=473"
last_edited: "2023-10-29T15:24:56Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Air A2179"
  - "Stubs"
infobox:
  Device: "MacBook Air A2179"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Air A2179 Not turning on, either 5V or 20V on USBC but with low current draw repair

## Problem description
When connected to the USB-C meter, the 820-01958 board draws very little current at either 5V or 20V. Not turning on and SLPS2R and AWAKE voltages/signals are cycling.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- MacBook A2179 not turning on.
- Little to no current draw as measured with a USBC ammeter.
- when measured, SLPS2R and AWAKE voltages/signals are cycling.

## Solution
### Diagnostic Steps
#### Check voltage and resistance to ground on PP5v_G3S
- When measured while the board is off, the resistance to ground on PP5v_G3S is typically large, well within the kilo-ohms.
  - If you measure less than 100 ohms, then you most likely have a short on this rail. See repair steps below.
- When the voltage is measured while the board is on, you should expect 5v.
  - Values less than 4.9v should be considered abnormal. If that's the case, see the relevant repair steps below

#### Check voltage and resistance to ground on PP3v3_G3S
- When measured while the board is off, the resistance to ground on PP3v3_G3S is typically large, well within the kilo-ohms.
  - If you measure less than 100 ohms, then you most likely have a short on this rail. See repair steps below.
- When the voltage is measured while the board is on, you should expect 3.3v.
  - Values less than 3.2v should be considered abnormal. If that's the case, see the relevant repair steps below

#### Check voltage and resistance to ground on PP1v8_G3S
- When measured while the board is off, the resistance to ground on PP1v8_G3S is typically large, well within the kilo-ohms.
  - If you measure less than 100 ohms, then you most likely have a short on this rail. See repair steps below.
- When the voltage is measured while the board is on, you should expect 1.8v.
  - Values less than 1.7v should be considered abnormal. If that's the case, see the relevant repair steps below

#### Check voltage and resistance to ground on PP3v_G3H
- When measured while the board is off, the resistance to ground on PP3v_G3S is typically large, well within the kilo-ohms.
  - If you measure less than 100 ohms, then you most likely have a short on this rail. See repair steps below.
- When the voltage is measured while the board is on, you should expect 3v.
  - Values less than 2.9v should be considered abnormal. If that's the case, see the relevant repair steps below

### Repair Steps
#### Short circuit on one of the rails or less than 100 ohms measured
[How to find short circuits](How_to_find_short_circuits.md)

- Inject 1V 5A to the shorted rail.
  - With either a thermal camera or your hand feel for the area that is heating up.
  - Identify and replace the shorted component.

#### No short is measured but voltage is still missing
Replace U7800.
