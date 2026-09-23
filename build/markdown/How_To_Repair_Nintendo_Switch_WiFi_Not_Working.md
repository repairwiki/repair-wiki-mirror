---
title: "How To Repair Nintendo Switch WiFi Not Working"
pageid: 8825
revid: 12845
kind: other
source: "https://repair.wiki/w/How_To_Repair_Nintendo_Switch_WiFi_Not_Working"
history: "https://repair.wiki/index.php?title=How_To_Repair_Nintendo_Switch_WiFi_Not_Working&action=history"
permalink: "https://repair.wiki/index.php?oldid=12845"
last_edited: "2025-11-23T12:46:09Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Nintendo Switch Lite"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Repair Nintendo Switch WiFi Not Working

## Problem description
Nintendo Switch Lite shows error 2110-1118, cannot connect to WiFi, no networks appear, or WiFi toggle is greyed out.

This fault commonly occurs due to:

1. Failed WiFi IC (Broadcom)
1. Missing / knocked-off resistors next to the USB-C port after a previous repair.

![Nintendo Switch Lite - WiFi Not Working[[File:SW WIFI IC LOCATION.png|thumb|Nintendo Switch Lite - WiFi IC Location\]\]](images/c/c5/SW_ERROR_SCREEN.png)

## Symptoms
- WiFi toggle missing or greyed out
- “Error Code: 2110-1118” when searching for networks
- No networks detected
- Bluetooth may also be affected (shares the same IC)
- Issues appear immediately after board repair (port replacement, power IC work, etc.)

## Solution
### Diagnostic Steps
#### 1. Software Ruling-Out
- Try factory reset (no data loss) → Settings → System → Formatting Options → Reset Cache
- Try full initialize (if customer approves)
- If WiFi toggle is missing: hardware fault confirmed

----
![Nintendo Switch Lite - Missing Resistors Next to the Type C Charge Port](images/9/92/SW_MISSING_RESIST.png)

#### 2. Visual Inspection (Board Level)
- Inspect the board area around USB-C
  - Look specifically for knocked-off resistors near the area circled in the provided image
- Inspect WiFi IC for:
  - Overheating marks
  - Reflow attempts
  - Physical damage
  - Cold solder pads
![Nintendo Switch Lite - Missing Resistors Soldered Back](images/b/b1/SW_RESISTORS_SOLDERED_BACK.png)

### Repair Steps
![Nintendo Switch Lite - WiFi Fixed Successfully After Replacing WiFi IC or Replacing Damaged/Missing Resistors](images/9/9c/SW_WIFI_FIXED_SUCCESSFULLY.png)

### Case 1 — WiFi IC Replacement
#### 1. Remove Old WiFi IC
- Preheat board
- Lift carefully to avoid pad damage

#### 2. Install Donor WiFi IC
- Important: Only use an original IC pulled from a donor Switch Lite
- Reball
- Align and reflow
- Inspect for bridges under microscope

#### 3. Testing
- Reassemble partially
- Power on → WiFi toggle should appear immediately
- Connect to network to confirm functionality

----

### Case 2 — Replace Missing Resistors Near USB-C
#### Common Fault
- One or more of the 4 tiny SMD resistors near the USB-C port are missing
- Usually damaged during USB-C desoldering

#### Steps
1. Clean area with flux
1. Inspect pads for ripping
1. Replace missing resistors
1. * match values from donor board
1. Microscope inspection for bridges or cold joints
1. Reassemble and test WiFi
1. WiFi should function properly
