---
title: "How To Turn On iPhone 14 to 16 Plus lower layer"
pageid: 7361
revid: 10938
kind: repair_guide
source: "https://repair.wiki/w/How_To_Turn_On_iPhone_14_to_16_Plus_lower_layer"
history: "https://repair.wiki/index.php?title=How_To_Turn_On_iPhone_14_to_16_Plus_lower_layer&action=history"
permalink: "https://repair.wiki/index.php?oldid=10938"
last_edited: "2025-08-30T17:56:52Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 14"
  - "Repair guides for iPhone 14 Plus"
  - "Repair guides for iPhone 15"
  - "Repair guides for iPhone 15 Plus"
  - "Repair guides for iPhone 16"
  - "Repair guides for iPhone 16 Plus"
  - "Repair guides for iPhone 16e"
infobox:
  Device: "iPhone 14, iPhone 14 Plus, iPhone 15, iPhone 15 Plus, iPhone 16, iPhone 16 Plus, iPhone 16e"
  Affects_parts: "Logic Board"
  Difficulty: "4. Specialist"
  Type: "Soldering"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Turn On iPhone 14 to 16 Plus lower layer

## Problem description
On newer iPhone models (14/Plus and above), the logic board is made of two sandwiched layers (upper + lower) and the CPU is on the lower layer. When troubleshooting short circuits on VDD_MAIN or other lines, technicians often separate the board to isolate and repair the issue.

However, after clearing the short, you may need to boot only the lower layer to confirm that the board is functional before reballing . Since the upper layer (with power button & interposer connection) is removed, you need a manual method to simulate power-on.

## Syptoms
- Device has a short on VDD_MAIN/VDD_BATT → board split to isolate.
- After repairing the short, phone does not auto-boot on lower layer.
- Need a way to trigger boot for testing.

## Repair Steps
1. Power Setup  Connect 4.2V from DC Power Supply (DCPS) to:  Positive lead → VDD_MAIN/VDD_BATT pad on lower board. Negative lead → Ground pad.
1. Locate Power Button Pin Identify the Power Button pin on the interposer connector of the lower board.
1. Simulate Power Press Use tweezers to short the Power Button pin to Ground momentarily. This mimics pressing the physical button.
1. Confirm Boot current draw on DCPS: If phone enters OS, lower layer repair is successful.![iPhone 14 / Plus](images/5/5d/Iphone14_-_plus_board.png)![iPhone 16 / Plus](images/a/a4/Iphone16-plus_board.png)![iPhone 15 / Plus](images/2/20/Iphone15-plus_board.png)
