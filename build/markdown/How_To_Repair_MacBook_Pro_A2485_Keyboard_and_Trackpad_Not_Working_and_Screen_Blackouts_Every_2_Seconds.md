---
title: "How To Repair MacBook Pro A2485 Keyboard and Trackpad Not Working and Screen Blackouts Every 2 Seconds"
pageid: 8652
revid: 12603
kind: other
source: "https://repair.wiki/w/How_To_Repair_MacBook_Pro_A2485_Keyboard_and_Trackpad_Not_Working_and_Screen_Blackouts_Every_2_Seconds"
history: "https://repair.wiki/index.php?title=How_To_Repair_MacBook_Pro_A2485_Keyboard_and_Trackpad_Not_Working_and_Screen_Blackouts_Every_2_Seconds&action=history"
permalink: "https://repair.wiki/index.php?oldid=12603"
last_edited: "2025-11-06T00:03:21Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A2485"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Repair MacBook Pro A2485 Keyboard and Trackpad Not Working and Screen Blackouts Every 2 Seconds

## Problem description
MacBook Pro A2485 powers on but keyboard and trackpad are unresponsive, and the display keeps turning off and on every few seconds. The system remains powered but only functions while connected to the charger. No visible liquid or corrosion damage.
![MacBook Pro A2485 Lid Angle Sensor](images/1/12/A2485_LAS.png)

## Symptoms
- Keyboard and trackpad not working.
- External keyboard/trackpad via USB work normally.
- Screen blacks out every 2 seconds, though the device remains powered.
- MacBook powers only when plugged into the charger — doesn’t boot from battery alone.
- No visible liquid or burnt components.
- Replacing the trackpad or battery does not resolve the issue.

## Solution
Replace the angle sensor flex cable (also known as the lid angle sensor flex).
![MacBook Pro A2485 Lid Angle Sensor Connector Location](images/a/a8/A2485_LAS_connector.png)
This flex cable communicates lid angle position; when shorted or faulty, it causes erratic power management signals, preventing keyboard/trackpad initialization and causing display blackouts.

### Diagnostic Steps
1. Visual Inspection
1. * Check for any bent or pinched flex cables near the hinge area.
1. * Inspect the angle sensor flex for visible damage, stress marks, or missing insulation.
1. Peripheral Substitution
1. * Try connecting a known-good trackpad and keyboard — if still nonfunctional, issue lies upstream (logic or sensor lines).
1. Angle Sensor Isolation Test
1. * Disconnect the angle sensor flex from the logic board.
1. * Reconnect battery and charger.
1. * If device now powers on normally and display stays stable → confirmed faulty angle sensor flex.

### Repair Steps
1. Power off and disconnect battery.
1. Open the back cover and locate the angle sensor flex (near the hinge area, connecting the display hinge to the logic board).
1. Disconnect the flex and visually inspect for damage.
1. Replace with a known-good or new OEM angle sensor flex.
1. Reconnect all cables (keyboard, trackpad, display, and battery).
1. Power on and confirm:
1. * Keyboard and trackpad function.
1. * Display stays stable.
1. * Device powers normally on battery.
