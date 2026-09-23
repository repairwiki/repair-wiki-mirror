---
title: "MacBook Air A1932 Not turning on, pulling 0.03-0.06A at 20V repair"
pageid: 164
revid: 492
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Air_A1932_Not_turning_on,_pulling_0.03-0.06A_at_20V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Air_A1932_Not_turning_on,_pulling_0.03-0.06A_at_20V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=492"
last_edited: "2023-10-29T15:26:31Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Air A1932"
  - "Stubs"
infobox:
  Device: "MacBook Air A1932"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera"
  Type: "Soldering, Software"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Air A1932 Not turning on, pulling 0.03-0.06A at 20V repair

## Problem description
No Power, 20v and ~0.03-0.06A current draw on the820-01521 logic board diagnosis and repair.

  - NOTE: This is an evolving issue, seen on many T2 series boards, and there is no fix for many of these cases as of 12/2/21. This article will be updated if/when a fix becomes available. See below for possible causes.**
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- MacBook not turning on
- Pulling ~0.03-0.06A current at 20v from USB-C as measured by USBC meter

## Solution
### Diagnostic Steps
#### Check for DFU or Recovery Mode
- Connect the MacBook to another Mac via the master port (*Left side, bottom port, closest to the trackpad)* and use Apple Configurator 2 to verify if it's in DFU mode.
- If in DFU mode, proceed to "Device stuck in DFU mode due to corrupt T2 firmware" repair steps.

#### Check for a short to ground on PP3v3_S5 or PP1v8_S5
If a short to ground is found, proceed to the "PP3v3_S5 or PP1v8_S5 short to ground" repair steps below.

### Repair Steps
#### Device stuck in DFU mode due to corrupt T2 firmware
- Revive or restore T2 firmware via Apple Configurator 2.
- Ensure you're running the latest macOS version for consistent results.
- [https://support.apple.com/guide/apple-configurator-mac/revive-or-restore-an-intel-based-mac-apdebea5be51/mac Follow the provided Apple support article for the procedure.]
- You should see a big square icon pop up that says "DFU" or rarely, "RECOVERY". Click the icon, Navigate to the top menu bar click "Actions" then "Advanced". Select Revive device. You will see a progress bar appear. This process can take anywhere from 2 minutes to over 30 minutes in some cases. It is important to note, if the device is in Recovery mode, the end user may have brought the device to another repair shop or Apple first, who attempted a DFU revive which failed. You may have a secondary issue if the revive fails again.
- **SELECTING RESTORE WILL WIPE ALL USER DATA!**

#### PP3v3_S5 shorted to ground
[How to find short circuits](How_to_find_short_circuits.md)

- If PP3v3_S5 is shorted to ground, pin 5 of U4885 is a good place to inject voltage to.
  - 1v at 5 amps is an appropriate voltage to inject into the line.
  - With voltage being injected, perform thermal imaging of the board. If thermal imaging is not available, feel around the board to see where it is getting warm. Once the area is localized, add a small amount of isopropyl alcohol to the area to localize the shorted component.
  - Once the shorted component is localized, replace the shorted component.

- If PP1v8_S5 is shorted to ground, CC722/CC723 is a good place to inject voltage to.
  - 1v at 5 amps is an appropriate voltage to inject into the line.
  - With voltage being injected, perform thermal imaging of the board. If thermal imaging is not available, feel around the board to see where it is getting warm. Once the area is localized, add a small amount of isopropyl alcohol to the area to localize the shorted component.
  - Once the shorted component is localized, replace the shorted component.

#### Forcing a firmware revive
- If no short is found on PP3v3_S5, and the device is not in DFU or recovery mode, you can try forcing a firmware revive.
- Attempt to restore BridgeOs firmware via Apple Configurator 2 by placing the device into DFU mode.
- STOP! Before you begin, is your Mac on the LATEST VERSION of MacOs? If not, update your system before proceeding. Forcing a MacBook into DFU mode, and attempting to restore BridgeOs firmware on a old version of MacOs may result in a bricked device.
- Selecting restore will wipe all user data.
- [https://support.apple.com/guide/apple-configurator-2/revive-or-restore-an-intel-based-mac-apdebea5be51/mac Follow the instructions on this Apple support article on how to revive or restore T2/BridgeOs firmware, including on how to force a Intel based MacBook into DFU mode by using a key combination.]
If the device fails the firmware revive or restore, the T2 chip or one of the NANDs is likely dead or is receiving unstable power from the PMIC (U7800) causing it to crash. If the device fails the firmware revive, you can try empirically replacing U7800.

  - Replacing U7800 should be seen as a last ditch effort, as it only works in a small amount of cases, and does not have a definitive diagnostic test to determine if it is bad.**
