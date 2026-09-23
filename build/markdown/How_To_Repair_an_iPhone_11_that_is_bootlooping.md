---
title: "How To Repair an iPhone 11 that is bootlooping"
pageid: 8306
revid: 12187
kind: repair_guide
source: "https://repair.wiki/w/How_To_Repair_an_iPhone_11_that_is_bootlooping"
history: "https://repair.wiki/index.php?title=How_To_Repair_an_iPhone_11_that_is_bootlooping&action=history"
permalink: "https://repair.wiki/index.php?oldid=12187"
last_edited: "2025-09-30T07:06:28Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 11"
infobox:
  Device: "iPhone 11"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Solering Iron, Hot Air Station"
  Difficulty: "3. Hard"
  Type: "Soldering"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Repair an iPhone 11 that is bootlooping

## Problem Description
This guide documents an iPhone 11 that was stuck in a bootloop due to a shorted I2C_AOP_SDA line caused by a faulty Audio IC (U4700).

Replacing the Audio IC resolves the short and allows the phone to boot normally.
----
![iPhone 11 - Audio IC (U4700) location on board](images/9/90/11-bootlooping-audio-ic-board.png)

## Symptoms
- Device bootloops endlessly (Apple logo → restart → repeat)
- No visible liquid damage or physical impact
- Restores with iTunes/3uTools fail or hang

----
![iPhone 11 - Audio IC (U4700) location on schematic](images/7/7c/11-audio-ic-schematic.png)

## Diagnostic Steps
1. Initial Test  Connect to DCPS → observe repeated current spikes and drops consistent with bootloop.
1. Check I²C Lines
1. * Measure resistance to ground on I²C_AOP_SDA and I²C_AOP_SCL.
1. * Where to measure: The easiest probing point is at the Front Proximity connector (FPC) on the logic board.
1. * Expected vs Actual Diode Mode Readings:
1. ** SDA (Data Line): Normally ~0.342 V. In our case, only 0.060 V, confirming the line was being pulled down/shorted.
1. ** SCL (Clock Line): ~0.318 V (within normal range).
1. Isolate Fault  Trace confirmed that the I²C_AOP_SDA line runs under U4700 (Audio IC). Remove U4700 → re-measure line → short clears.
1. Confirm Diagnosis![iPhone 11 Front prox pins to measure](images/9/93/11-bootlooping_front_prox.png)Test boot with U4700 removed → phone boots into iOS normally (without audio). This confirms U4700 was the cause of the short.

----

## Repair Steps
1. Remove U4700 Audio IC.
1. Clean pads on PCB and prepare a replacement U4700 (new or donor).
1. Reball or use pre-balled replacement IC, re-install onto board.
1. Power on and verify I2C_AOP_SDA line is no longer shorted.
1. Confirm full boot into iOS and test all audio functions (speaker, mic, earpiece).
