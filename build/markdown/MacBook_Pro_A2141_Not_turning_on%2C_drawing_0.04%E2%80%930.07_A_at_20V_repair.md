---
title: "MacBook Pro A2141 Not turning on, drawing 0.04–0.07 A at 20V repair"
pageid: 110
revid: 260
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A2141_Not_turning_on,_drawing_0.04%E2%80%930.07_A_at_20V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A2141_Not_turning_on,_drawing_0.04%E2%80%930.07_A_at_20V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=260"
last_edited: "2023-10-01T15:50:52Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A2141"
  - "Stubs"
infobox:
  Device: "MacBook Pro A2141"
  Affects_parts: "Motherboard"
  Needs_equipment: "Multimeter"
  Type: "Software"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A2141 Not turning on, drawing 0.04–0.07 A at 20V repair

## Problem description
Facing an issue with the MacBook Pro A2141 (820-01700) displaying 20V and a very low current draw of 0.04 to 0.07A on the USB-C meter.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- MacBook not turning on
- PP3V3_S5 and PP1V8_S5 missing
- PPBUS_G3H at 12.3 V
- Pulling 0.04 to 0.07A on the USB-C meter.

## Solution
The T2 chip is not properly communicating to the Calpe PMU (U7800), likely due to firmware corruption. This can also occur after replacing the PMU itself, or Ocarina, which is the SSD PMIC. Assemble the device and force it into DFU mode via the power button and keyboard.

- Ensure the MacBook is running the latest macOS version for consistent results.
- [https://support.apple.com/guide/apple-configurator-mac/revive-or-restore-an-intel-based-mac-apdebea5be51/mac Follow the provided Apple support article for the procedure.]
- Once plugged in, open Apple Configurator 2. You should see a big square icon pop up that says "DFU" or rarely, "RECOVERY". Click the icon, Navigate to the top menu bar click "Actions" then "Advanced". Select Revive device. You will see a progress bar appear. This process can take over 30 minutes in some cases as Apple Configurator 2 now reinstalls the OS in addition to the M1's firmware. Data will still be retained with the revive option.
- Be cautious that selecting "Restore" will wipe all user data.
