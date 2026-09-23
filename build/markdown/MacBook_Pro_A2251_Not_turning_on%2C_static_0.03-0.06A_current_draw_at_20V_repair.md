---
title: "MacBook Pro A2251 Not turning on, static 0.03-0.06A current draw at 20V repair"
pageid: 75
revid: 521
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A2251_Not_turning_on,_static_0.03-0.06A_current_draw_at_20V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A2251_Not_turning_on,_static_0.03-0.06A_current_draw_at_20V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=521"
last_edited: "2023-10-29T15:28:25Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A2251"
  - "Stubs"
infobox:
  Device: "MacBook Pro A2251"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A2251 Not turning on, static 0.03-0.06A current draw at 20V repair

## Problem description
Addressing issues with MacBook (820-01949) exhibiting no power, and an amp draw of ~0.03-0.06A at 20V.

## Symptoms
- MacBook not turning on
- When input power is measured with a USBC ammeter, a current draw of 0.03-0.06A at 20V is observed.
![U9000 (Figure 1) -- No image yet. Help expand this page by uploading it](images/3/30/Placeholder_image.jpg)
![U7800 (Figure 2) -- No image yet. Help expand this page by uploading it](images/3/30/Placeholder_image.jpg)
## Solution
### Diagnostic Steps
#### Check for DFU or Recovery Mode
- Connect the MacBook to another Mac via the master port and use Apple Configurator 2 to check for DFU mode.
- If in DFU mode, proceed to "Device stuck in DFU or recovery mode due to corrupt T2 firmware" repair steps.

#### Check for PP3v3_S5 Short to Ground
- If a short to ground is identified, proceed to the "PP3v3_S5 short to ground" repair steps.

#### Check Resistance on PP2v5_NAND_SSD_0
- Normal resistance can range from >1MΩ to 60Ω.
- Resistance between 1-3Ω suggests SSD/NAND failure.

#### Inspect U9000 for Corrosion
- Inspect U9000 (Figure 1) for corrosion, especially around its location.
- Corroded U9000 can be reballed to potentially resolve the issue.

### Repair Steps
#### Device stuck in DFU mode due to corrupt T2 firmware
- Revive or restore T2 firmware via Apple Configurator 2.
- Ensure you're running the latest macOS version for consistent results.
- Follow the provided [https://support.apple.com/guide/apple-configurator-mac/revive-or-restore-an-intel-based-mac-apdebea5be51/mac Apple support article] for the procedure.
- You should see a big square icon pop up that says "DFU" or rarely, "RECOVERY". Click the icon, Navigate to the top menu bar click "Actions" then "Advanced". Select Revive device. You will see a progress bar appear. This process can take anywhere from 2 minutes to over 30 minutes in some cases. It is important to note, if the device is in Recovery mode, the end user may have brought the device to another repair shop or Apple first, who attempted a DFU revive which failed. You may have a secondary issue if the revive fails again.
    - SELECTING RESTORE WILL WIPE ALL USER DATA!**
- Possible causes for a device to fail a DFU revive:
- #Short to ground on PP2v5_NAND_SSD_0
- #Absent U9000 voltages. (PP0v9_SSD_0, PPVCCQ_ANI_SSD0 (1.8v) )
- #Failed Trackpad (Will almost always show the Apple logo before failing the process.)
- #Failed NAND
- #Failed T2 or T2 RAM.
- #Cracked solder joints under T2 chip (Uncommon, usually only suspected if device was dropped prior to initial failure.)

#### PP3v3_S5 Shorted to Ground
- Locate and replace the shorted component.
- Use a small gauge wire to inject 1V at 5A into the line.
- Perform thermal imaging to locate the area getting warm.
- Apply isopropyl alcohol to locate the shorted component.
- Replace the identified shorted component.

#### U9000 Corroded or Damaged
- If corroded, reball the IC; replacement is usually not required.
- If damaged or burned, replace the IC (part: 338S00410).

#### Force Firmware Revive
- Attempt to restore BridgeOs firmware by placing the device into DFU mode.
- Follow Apple's instructions, including updating macOS to the latest version.
- If firmware revive fails, consider replacing U7800 (Figure 2) as a last resort.
- Note: U7800 replacement has limited success and lacks a definitive diagnostic test.
