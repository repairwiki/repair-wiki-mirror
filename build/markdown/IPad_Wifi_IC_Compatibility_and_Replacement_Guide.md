---
title: "IPad Wifi IC Compatibility and Replacement Guide"
pageid: 8711
revid: 12777
kind: other
source: "https://repair.wiki/w/IPad_Wifi_IC_Compatibility_and_Replacement_Guide"
history: "https://repair.wiki/index.php?title=IPad_Wifi_IC_Compatibility_and_Replacement_Guide&action=history"
permalink: "https://repair.wiki/index.php?oldid=12777"
last_edited: "2025-11-19T20:54:05Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPad 10"
  - "Repair guides for iPad 6"
  - "Repair guides for iPad 7"
  - "Repair guides for iPad 8"
  - "Repair guides for iPad 9"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPad Wifi IC Compatibility and Replacement Guide

## Problem description
Many technicians encounter “No Wi-Fi”, grayed-out Wi-Fi toggle, or Wi-Fi IC overheat/no detection on iPads.

However, confusion often arises when sourcing replacement Wi-Fi ICs, because Wi-Fi-only and Cellular iPad logic boards use different Wi-Fi ICs — and they are not cross-compatible.

Installing the wrong variant will cause the Wi-Fi module to fail initialization, resulting in no Wi-Fi detection, no MAC address.
![iPad 7,8 & 9 - (WiFi + Cellular Model) WiFi IC](images/f/f0/Ipadwificellular.png)
![iPad 7,8 & 9 - (WiFi Only Model) WiFi IC](images/7/79/Ipadwifionly.png)

## Symptoms
- Wi-Fi toggle grayed out in settings.
- Wi-Fi MAC address missing in “About” section.
- Board heating around Wi-Fi IC area.
- Replacing with an IC from another variant (e.g., from Wi-Fi model to Cellular model) results in no detection.

## Solution
Identify the correct Wi-Fi IC part number for the specific iPad model and variant (Wi-Fi or Cellular).

Always use the exact same IC model from a donor board of the same type.

Wi-Fi and Cellular iPads differ in the Wi-Fi/BT combo chip, RF routing, and antenna matching network, even when the logic board layout looks identical.

  - NOTE**: When replacing the WiFi IC, ensure the new IC has the exact same part number as the original. Mismatched WiFi IC numbers are not cross-compatible and will result in no WiFi functionality.

| iPad Model | Board Type | Wi-Fi IC Chip ID | Notes |
| --- | --- | --- | --- |
| iPad 6 (WiFi) | A1893 | 339S00446 |  |
| iPad 6 (WiFi + Cellular) | A1954 | 339S00445 |  |
| iPad 7 (WiFi) | A2197 | 339S00448 |  |
| iPad 7 (WiFi + Cellular) | A2200, A2198 | 339S00445 |  |
| iPad 8 (WiFi) | A2270 | 339S00448 |  |
| iPad 8 (WiFi + Cellular) | A2428, A2429 (Global), A2430 (China) | 339S00445 |  |
| iPad 9 (WiFi) | A2602 | 339S00448 |  |
| iPad 9 (WiFI + Cellular) | A2603, A2604, A2605 | 339S00445 |  |

### Diagnostic Steps
1. Confirm Variant
1. * Check back housing model (A****).
1. * Cross-reference with Wi-Fi or Cellular variant.
1. Check Wi-Fi IC Reference
1. * Use ZXW or BoardView to locate the Wi-Fi module part number.
1. * Identify whether it’s 339S0058 (Wi-Fi) or 339S0059 (Cellular) etc.
1. Resistance / Power Test
1. * Measure power rails next to Wi-Fi IC.
1. * If shorted, isolate Wi-Fi IC.

### Repair Steps
1. Disconnect battery and shield around Wi-Fi module.
1. Preheat board.
1. Use hot air to lift Wi-Fi IC carefully.
1. Clean pads, check for lifted traces.
1. Replace with correct Wi-Fi IC.
1. Reassemble and test Wi-Fi detection.
