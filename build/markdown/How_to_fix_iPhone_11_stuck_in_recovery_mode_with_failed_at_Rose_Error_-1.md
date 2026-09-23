---
title: "How to fix iPhone 11 stuck in recovery mode with failed at Rose Error -1"
pageid: 8205
revid: 12056
kind: repair_guide
source: "https://repair.wiki/w/How_to_fix_iPhone_11_stuck_in_recovery_mode_with_failed_at_Rose_Error_-1"
history: "https://repair.wiki/index.php?title=How_to_fix_iPhone_11_stuck_in_recovery_mode_with_failed_at_Rose_Error_-1&action=history"
permalink: "https://repair.wiki/index.php?oldid=12056"
last_edited: "2025-09-24T13:17:06Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 11"
  - "Repair guides for iPhone 11 Pro"
  - "Repair guides for iPhone 11 Pro Max"
infobox:
  Device: "iPhone 11, iPhone 11 Pro, iPhone 11 Pro Max"
  Needs_equipment: "Soldering Iron, Hot Air Station, Reballing Stencil"
  Affects_parts: "Main Logic Board"
  Difficulty: "4. Specialist"
  Type: "Soldering"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How to fix iPhone 11 stuck in recovery mode with failed at Rose Error -1

## Problem Description
An iPhone 11 or 11 Pro is stuck in recovery mode and fails to restore when flashing with 3uTools. The flash process typically reaches 90% and then fails with Error Code -1.

This is most often caused by the Rose IC not being detected. On the iPhone 11 (non-Pro), this can happen because of:

- A bad Rose IC
- Cracked solder joints or separation between the top and bottom logic board layers after a drop, which interrupts Rose IC communication

On iPhone 11 Pro / Pro Max models, the Rose IC sits on the top board, so interposer issues are not usually responsible — the fault is almost always with the IC itself.
![iPhone 11-11 Pro Max Flashing Error (ROSE IC)](images/3/36/11-rose-flashing-error.png)
----

## Symptoms
- Device is permanently in Recovery Mode.
- Flashing fails at ~90% with error (-1) in 3uTools.
- Unplugging all flexes and trying to flash doesn't fix the issue.

----
![iPhone 11 Rose IC location](images/6/63/11-rose-location.png)

## Diagnostic Steps
1. Visual Inspection
1. * Open the device and check for signs of water damage, board warping, or physical cracks.
1. * Look closely for separation between board layers.
1. Restore Attempt
1. * Attempt a full flash using 3uTools.
1. * Confirm the process fails at 90% with error -1.
1. iSocket Test (Non-Pro Models)
1. * Separate the logic board layers carefully.
1. * Place both layers in an iSocket/test fixture and attempt flashing again.
1. * If flash succeeds: The fault is with the interposer/middle-layer connection — reball the board layers and rejoin them.
1. * If flash fails: Move on to Rose IC diagnosis and replacement.
1. Skip iSocket Test on Pro Models
1. * Since Rose IC is on the top board, interposer issues are not the cause.

----
![iPhone 11 Pro & Pro Max Rose IC location](images/9/9f/11p-rose-location.png)

## Repair Steps
### Solution 1: Reball the Middle Layer (iPhone 11)
- Clean and reball all interposer pads on top and bottom board layers.
- Rejoin board with a preheater and proper alignment jig.
- Test flash again — in many cases this restores proper Rose IC communication.

### Solution 2: Replace or Reball Rose IC
- Locate Rose IC on the bottom board (11) or top board (11 Pro/Pro Max).
- Remove and replace with donor chip.
- Clean the pads, reflow, and reassemble.

### Solution 3: Final Flash & Verification
- Reassemble iPhone partially and attempt a full restore.
- If successful, phone should boot normally and pass activation.
- Perform a full functional check (Wi-Fi, LTE, Face ID, etc.) before final assembly.
