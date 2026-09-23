---
title: "How to Fix iPhone 15 Rear Camera Not Switching Lenses Intermittent Camera"
pageid: 6747
revid: 10139
kind: repair_guide
source: "https://repair.wiki/w/How_to_Fix_iPhone_15_Rear_Camera_Not_Switching_Lenses_Intermittent_Camera"
history: "https://repair.wiki/index.php?title=How_to_Fix_iPhone_15_Rear_Camera_Not_Switching_Lenses_Intermittent_Camera&action=history"
permalink: "https://repair.wiki/index.php?oldid=10139"
last_edited: "2025-08-11T02:11:37Z"
contributors:
  - "VCCBoardRepairs"
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 15"
infobox:
  Device: "iPhone 15"
  Affects_parts: "Main Logicboard"
  Needs_equipment: "Microscope, Soldering iron"
  Difficulty: "3. Hard"
  Type: "Soldering"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How to Fix iPhone 15 Rear Camera Not Switching Lenses Intermittent Camera

## Problem description
iPhone 15 units experience an issue where the rear camera will not switch from 0.5x (ultra-wide) to 1x (wide) or 2x(telephoto), or switches intermittently. This is often due to two capacitors near the rear camera connector developing cold solder joints (improper solder bonding) or failing. These capacitors are part of the camera power circuit — when the connection is unstable, the system cannot properly drive the other camera modules.

![Capacitors located on the iPhone 15 camera power circuit](images/1/1c/Capacitors.png)

## Symptoms
- Camera stuck on 0.5x
- Lag or delay when switching between lenses
- Camera intermittently switches but fails again shortly

## Diagnostic steps
1. Confirm the Symptom
1. * Open the Camera app.
1. * Attempt to switch between 0.5x, 1x, and 2x zoom.
1. * Note if the camera is stuck on one lens (usually 0.5x) or switching is slow/intermittent.
1. Rule Out Software Issues
1. * Force close the Camera app and reopen it.
1. * Test in third-party camera apps (e.g., Instagram, Snapchat).
1. * Update iOS to the latest version.
1. * Perform a hard reset of the phone.
1. * If the issue persists, proceed to hardware diagnostics.
1. Inspect Camera Connector
1. * Disassemble the phone and visually inspect the rear camera connector on the logic board for debris, corrosion, or mechanical damage.
1. * Clean with IPA (isopropyl alcohol) if necessary.
1. Test with a Known Good Camera Module
1. * Connect a known working rear camera assembly to the board.
1. * If switching works normally, the fault is in the customer’s camera module (replace camera).
1. * If switching still fails, the fault is on the logic board — proceed to step 5.
1. Probe the Lens Switching Capacitors
1. * Locate the two capacitors near the rear camera connector (refer to the location photo in the guide).
1. * Inspect for cold solder joints (dull, cracked, or uneven solder).

## Repair steps
1. Preparation
1. * Disconnect battery.
1. * Shield surrounding components with Kapton tape.
1. Remove Glue
1. * Carefully soften and scrape away the factory glue covering the capacitors using hot air.
1. Reflow or Re-solder
1. * Apply flux around both capacitors.
1. * Using a soldering iron or hot air, reflow both ends of each capacitor.
1. Clean Area
1. * Remove excess flux with isopropyl alcohol and an ESD brush.
1. Reassemble & Test
1. * Reconnect battery, boot device, and test camera switching between all lenses.
