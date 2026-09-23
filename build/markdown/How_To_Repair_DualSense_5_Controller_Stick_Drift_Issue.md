---
title: "How To Repair DualSense 5 Controller Stick Drift Issue"
pageid: 9599
revid: 13910
kind: other
source: "https://repair.wiki/w/How_To_Repair_DualSense_5_Controller_Stick_Drift_Issue"
history: "https://repair.wiki/index.php?title=How_To_Repair_DualSense_5_Controller_Stick_Drift_Issue&action=history"
permalink: "https://repair.wiki/index.php?oldid=13910"
last_edited: "2026-02-09T07:08:14Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Sony Dualsense Controller"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Repair DualSense 5 Controller Stick Drift Issue

## Problem description
Stick drift is a common issue where the controller’s analog stick registers movement even when you aren’t touching it. This makes characters move on their own, menus scroll by themselves, and generally interferes with gameplay. (See Fig. 1)
![Figure 1 -- DualSense 5 Controller Showing Drift in Gamepad Tester Software when the stick is not moved in real life](images/3/33/Dualsense-stick-drift.png)

## Symptoms
- Character or cursor moves without input
- Stick input appears when controller is idle
- Drift occurs only in certain directions
- Slight drift even when stick is centered
- Drift persists across games and menus

![Figure 2 -- DualSense 5 Controller Joystick Module](images/8/87/Dualsense-5-joystick-module.png)
![Figure 3 -- DualSense 5 Controller Joystick Solder Points](images/2/26/Dualsense-5-joystick-solder.png)
![Figure 4 -- Removing DualSense 5 Controller Joystick Module](images/1/10/Dualsense-5-joystick-desolder.png)

## Solution
### Diagnostic Steps
----

1. Confirm the Drift
1. * Connect the controller to a PS5 or PC.
1. * Leave the analog stick untouched.
1. * You can use a controller testing software on PC:  https://ds.daidr.me/
1. * Observe:
1. ** Character or cursor movement
1. ** Axis movement in controller test software
1. Rule Out Software Causes
1. * Reset the controller using the rear reset pin (5–10 seconds).
1. * Update controller firmware on PS5.
1. * Re-test for drift.
1. * If drift persists → hardware fault confirmed.
1. Check Drift Severity
1. * Slight, inconsistent drift → likely contamination.
1. * Strong, constant drift in one direction → worn potentiometer.
1. * Drift on both axes → joystick module failure.
1. Inspect for Physical Wear
1. * Rotate and press the stick.
1. * Note:
1. ** Loose feel
1. ** Grinding or resistance
1. ** Stick not returning to center
1. Decide Repair Path
1. * Minor drift → cleaning attempt.
1. * Persistent drift → joystick module replacement.

----

### Repair Steps
#### Repair Option 1: Cleaning (Temporary / Minor Drift)
1. Power off and disconnect the controller.
1. Remove faceplate and access the analog stick.
1. Blow compressed air around the base of the stick.
1. Apply 90%+ isopropyl alcohol or contact cleaner to the stick base.
1. Rotate the stick fully in all directions for 20–30 seconds.
1. Allow to dry completely.
1. Reassemble and test.

✅ Use this if drift is mild or intermittent.
----

#### Repair Option 2: Joystick Module Replacement (Permanent Fix)
1. Fully disassemble the controller.
1. Remove battery and internal shields.
1. Expose the joystick module PCB.
1. Desolder the joystick module:
1. * Add low melt solder to joystick solder points (See Fig. 3)
1. * Heat evenly
1. * Avoid lifting pads
1. Clean solder pads thoroughly.
1. Install a new joystick module (OEM or Hall-effect upgrade).
1. Solder all anchor and signal pins securely.
1. Inspect joints under magnification.
1. Reassemble controller.
1. Test analog stick response.

✅ This is the recommended long-term fix for stick drift.
