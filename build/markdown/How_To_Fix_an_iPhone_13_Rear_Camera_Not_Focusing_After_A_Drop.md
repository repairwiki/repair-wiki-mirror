---
title: "How To Fix an iPhone 13 Rear Camera Not Focusing After A Drop"
pageid: 8381
revid: 12264
kind: other
source: "https://repair.wiki/w/How_To_Fix_an_iPhone_13_Rear_Camera_Not_Focusing_After_A_Drop"
history: "https://repair.wiki/index.php?title=How_To_Fix_an_iPhone_13_Rear_Camera_Not_Focusing_After_A_Drop&action=history"
permalink: "https://repair.wiki/index.php?oldid=12264"
last_edited: "2025-10-08T12:29:11Z"
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

# How To Fix an iPhone 13 Rear Camera Not Focusing After A Drop

## Problem description
The iPhone 13 rear camera fails to focus after a hard drop. The camera opens normally, but the image remains blurry and the lens fails to adjust focus. Replacing the camera module does not fix the problem.

This fault is caused by cracked or lifted solder joints between the logic-board layers, interrupting communication lines (I2C2) between the Camera PMU, Strobe IC and camera module. These breaks occur due to mechanical shock from the drop, which flexes the multilayer board and fractures inter-layer connections.
![iPhone 13 - i2c2 lines](images/c/ce/13_camera_layer_1.png)

## Symptoms
- Rear camera fails to focus or constantly hunts
- Replacing the camera module does not solve the issue
- Front camera works normally
- Device otherwise powers and functions normally

### Diagnostic Steps
1. Visual Inspection
1. * Inspect camera flex connector area under microscope for board flex, delamination.
1. * Check for signs of prior impact near the rear camera section (especially upper board area).
1. Test With Known Good Camera
1. * Confirm that replacing the rear camera does not restore focus.
1. * This rules out Camera failure and confirms the issue is board-level.

### Repair Steps
1. Remove Logic Board
1. * Disassemble device completely and remove the double-stacked logic board assembly.
1. * Disconnect all flexes.
1. Perform Layer Reball (Reflow Not Recommended)
1. * Preheat using bottom heater.
1. * Separate top and bottom board layers carefully.
1. * Reball interposer pads with 148/158 solder paste.
1. * Align and rejoin layers.
1. Post-Reball Verification
1. * Check for shorts.
1. Reassemble and Test
1. * Assemble logic board, connect camera, and test focus.
1. * Camera should now focus correctly across all modes (Photo, Portrait, Video).
