---
title: "MacBook Pro A2338 Clicking sound from system board, showing 5v on USB-C amp meter repair"
pageid: 57
revid: 532
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A2338_Clicking_sound_from_system_board,_showing_5v_on_USB-C_amp_meter_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A2338_Clicking_sound_from_system_board,_showing_5v_on_USB-C_amp_meter_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=532"
last_edited: "2023-10-29T15:29:25Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A2338"
  - "Stubs"
infobox:
  Device: "MacBook Pro A2338"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A2338 Clicking sound from system board, showing 5v on USB-C amp meter repair

## Problem description
Clicking sound from the system board with 5V measured by the USB-C amp meter.

## Symptoms
- Clicking sound from the system board.
- 5V reading on the USB-C amp meter.

## Solution
### Diagnostic Steps
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
#### Measure voltage on PP3v8_AON
Normal voltage = 3.8v. You will likely find that the voltage is low and pulsing slightly or completely absent. This confirms the diagnosis.

#### Perform a visual inspection of the system board
This failure is very uncommon without liquid damage. Often times, you will find that one of the 3v8_AON MOSFETs will be corroded, or that U5700 itself will be corroded. If the MOSFETs (Q5800, Q5820, or Q5840) are corroded, proceed to the Repair Steps below for "PP3v8_AON creation MOSFETs corroded" below. If the PP3v8_AON buck converter IC (U5700) is corroded, proceed to the "PP3v8_AON buck converter IC corroded" repair steps below.

### Repair Steps
#### PP3v8_AON creation MOSFETs corroded
- Replace Q5800, Q5820, and Q5840 together. It's important to replace all 3 MOSFETs at the same time as if one MOSFET failed, it may have damaged the others. Replacement of U5700 is not necessary as long as it isn't corroded and as long as the clicking sound does not persist after replacement of the MOSFETs.

#### PP3v8_AON buck converter IC corroded
- Replace U5700. Replacement of the PP3v8_AON creation MOSFETs is not required unless they are corroded or if the clicking sound persists after replacement of U5700.

Verify correct voltage on PP3v8_AON after the relevant repair is performed.
