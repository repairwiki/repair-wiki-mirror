---
title: "Nintendo Switch Video Output Issues: No Video or HDMI Output"
pageid: 4205
revid: 7203
kind: repair_guide
source: "https://repair.wiki/w/Nintendo_Switch_Video_Output_Issues:_No_Video_or_HDMI_Output"
history: "https://repair.wiki/index.php?title=Nintendo_Switch_Video_Output_Issues:_No_Video_or_HDMI_Output&action=history"
permalink: "https://repair.wiki/index.php?oldid=7203"
last_edited: "2025-05-29T20:39:03Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Nintendo Switch"
  - "Stubs"
infobox:
  Device: "Nintendo Switch"
  Affects_parts: "Motherboard"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope, Multimeter"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Nintendo Switch Video Output Issues: No Video or HDMI Output

## Problem description
The console turns on and charges fine, but there is no video output/HDMI output when docked.
![Nintendo Switch Diode Mode Readings from a Mechanic T824 Reader](images/2/2d/Nintendo_Switch_Diode_Mode_Readings_Mechanic_T824.jpg)

## Symptoms
- Console does not display any video when placed on dock

### Diagnostic Steps
The first step is to try with a known good dock.

Inspect the USB-C port for any physical damage, such as bent pins, missing pins, or liquid damage. If you have a Mechanic T284 USB tester, compare your readings with the image on the right.

Check for shorts around the M92T36 IC. This chip negotiates power through the USB-C port. Below is an image with capacitors to check.
![M92T32 Caps to Check](images/d/d0/M92T32.png)
The next area to check is the chokes near the PI3USB IC. The chokes must have continuity in parallel but not in cross.
![P13 Chokes Location](images/1/1a/P13_Chokes.png)

The next component to check is the PI3USB30532 IC. This component is critical for USB-C data switching, including video output via the dock’s HDMI.
![P13 Caps that should be checked](images/a/a9/P13_shorts.png)
In most cases, when the console turns on and charges, the causes for no video output are blown chokes or a faulty PI3USB30532.

### Repair Steps
The M92T36 and PI3USB30532 are widely available and relatively cheap.

The replacement process is similar for both chips. Use your hot air station to desolder the old chips, clean the old solder, add new solder to the pads, and use your hot air station to solder the IC. Use your soldering iron with a fine tip to touch up any connections that may not be secure.

The chokes are easy to replace. Use your hot air station to desolder them, apply new solder to the board, and solder the new chokes. Be careful not to use excessive air, or you risk the choke flying off.

## Final Testing
  - Basic Display and Audio Test**:

- Connect Switch to a known good dock with a quality HDMI cable and official AC adapter.
- Power on, dock, and check for clear video (no artifacts/flickering) and audio (no static/dropouts) on TV/monitor.
- Test with a game to confirm stability.
  - Auto-Detect Resolution Test**:

- Go to **System Settings > TV Output > TV Resolution**, select **Automatic**.
- Confirm auto-detected resolution (typically 1080p) and test switching (1080p, 720p, 480p).

Also check every other function of the console to make sure no new issues have surfaced.
