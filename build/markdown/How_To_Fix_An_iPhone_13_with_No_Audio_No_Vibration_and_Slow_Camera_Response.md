---
title: "How To Fix An iPhone 13 with No Audio No Vibration and Slow Camera Response"
pageid: 8754
revid: 12743
kind: other
source: "https://repair.wiki/w/How_To_Fix_An_iPhone_13_with_No_Audio_No_Vibration_and_Slow_Camera_Response"
history: "https://repair.wiki/index.php?title=How_To_Fix_An_iPhone_13_with_No_Audio_No_Vibration_and_Slow_Camera_Response&action=history"
permalink: "https://repair.wiki/index.php?oldid=12743"
last_edited: "2025-11-18T21:18:45Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 13"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix An iPhone 13 with No Audio No Vibration and Slow Camera Response

## Problem description
iPhone 13 shows multiple symptoms related to audio output, vibration feedback, and camera performance. Common field reports show that a damaged or failing U8400 IC can cause these issues.
![iPhone 13 - U8400 IC Location On Board](images/c/c9/Iphone_13_nosound_board.png)

## Symptoms
- No ringer / no bottom speaker output
- No vibration (Taptic Engine non-functional)
- Camera app freezes or has delayed response
- No improvement even after replacing bottom speaker, Taptic Engine, or restoring firmware

## Solution
### Diagnostic Steps
### 1. Visual Inspection
- Inspect U8400 area for:
  - Cracked IC
  - Burn marks on IC
  - Impact marks

----
![iPhone 13 - U8400 IC Location on BoardView Software](images/5/5f/Iphone_13_nosound_boardview.png)

### 2. Peripheral Testing
- Connect known-good bottom speaker → test ringer
- Connect known-good Taptic Engine → test vibration
- Open Camera → check for slow UI or freeze

If all peripherals test good but symptoms persist → U8400 fault confirmed.
----

## Repair Steps
### 1. Board Preparation
- Remove logic board
- Shield surrounding areas

----

### 2. IC Removal
- Apply flux
- Heat U8400 gently
- Lift IC without disturbing surrounding components

----

### 3. Pad Cleanup
- Wick pads carefully
- Inspect for:
  - Torn pads

----

### 4. Reball New U8400 IC
- Use correct stencil
- Reball and inspect under microscope

----

### 5. Install New IC
- Align using boardview orientation
- Reflow until IC settles naturally
- Allow to cool fully

----

### 6. Post-Repair Testing
- Reassemble device
- Test:
  - Ringer output
  - Vibration
  - Camera app responsiveness
  - System haptics

All functions should return to normal after successful U8400 replacement.
