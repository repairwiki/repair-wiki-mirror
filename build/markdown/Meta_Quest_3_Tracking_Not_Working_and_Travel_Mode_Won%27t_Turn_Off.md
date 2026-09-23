---
title: "Meta Quest 3 Tracking Not Working and Travel Mode Won't Turn Off"
pageid: 9841
revid: 14241
kind: repair_guide
source: "https://repair.wiki/w/Meta_Quest_3_Tracking_Not_Working_and_Travel_Mode_Won't_Turn_Off"
history: "https://repair.wiki/index.php?title=Meta_Quest_3_Tracking_Not_Working_and_Travel_Mode_Won't_Turn_Off&action=history"
permalink: "https://repair.wiki/index.php?oldid=14241"
last_edited: "2026-03-31T18:17:09Z"
contributors:
  - "Timleonhardi"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Meta Quest 3"
  - "Stubs"
infobox:
  Device: "Meta Quest 3"
  Affects_parts: "Tracking"
  Type: "Part replacement"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Meta Quest 3 Tracking Not Working and Travel Mode Won't Turn Off

## Problem description
Meta Quest 3 refuses to track the environment, won't set boundary and keeps reverting to Travel Mode no matter what you do. This usually shows up as a Travel Mode prompt, headset-only tracking that won't switch off, or a complete failure to detect the play space.

![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
The device will display a prompt stating "Your Room Boundary and most apps won't work because your headset can't detect your movement right now" "If you're in a moving vehicle, turn on travel mode and remember to stay seated"

The device will constantly revert to Travel mode even if you manage to disable travel mode.

When forced out of Travel Mode, the virtual environment instantly launches in a random direction and jitters uncontrollably making the headset unusable. (Faulty IMU Experience)

## Solution
In my experience this is likely a hardware issue. But in rare circumstances it could be software related. But the usual problem is with Front Camera tracking.

### Diagnostic Steps
Force headset out of Travel Mode via Settings and Observe what happens (It may take a few attempts to get the headset to turn off travel mode)

Force Restart the headset (Not sleep mode)

Clear Guardian/Boundary Data (Settings - Guardian)

Check if the Passthrough Cameras Work (If Passthrough doesn't work proceed to replacing the front camera)

Optional: Factory Reset the headset to fully rule out software (Warning: If the cameras or sensors are indeed the problem, factory resetting the headset will soft brick the headset. Tracking is required to set up the headset. Without tracking the menu to setup the headset will not be able to be found and you will be stuck until the tracking issue is repaired. Because the headset is still playable in travel mode use this option with caution.)

### Repair Steps
Disassemble the headset to remove the front cover. Warning: There is several sensors that can be damaged when removing the front cover. Use caution.

If passthrough worked in the diagnostic steps, proceed with changing depth camera which is location in the middle between the two front cameras.

If passthrough didn't work, replace front cameras and possibly depth camera as well. (Some places sell used front covers with cameras preinstalled, no calibration issues have been found replacing any of the front sensors)

Note: the cameras and sensor use a thermal putty to keep them cool similar to the thermal putty found in newer Xbox's. Make sure there is new thermal putty on the replacement camera or sensor to prevent overheating.
