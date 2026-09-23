---
title: "MacBook Pro A2251 Not turning on, 0.23-0.31A current draw at 5V Cycling or not cycling repair"
pageid: 74
revid: 520
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A2251_Not_turning_on,_0.23-0.31A_current_draw_at_5V_Cycling_or_not_cycling_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A2251_Not_turning_on,_0.23-0.31A_current_draw_at_5V_Cycling_or_not_cycling_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=520"
last_edited: "2023-10-29T15:28:22Z"
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

# MacBook Pro A2251 Not turning on, 0.23-0.31A current draw at 5V Cycling or not cycling repair

## Problem description
Addressing issues with MacBook (820-01949) exhibiting no power, and an amp draw of ~0.23-0.31A at 5V, either cycling or not cycling.

Potential causes include failed or corroded CD3217 (Figure 1), corroded TBT ROM (Figure 2), incompatible CD3217 replacement, or device stuck in DFU mode.

## Symptoms
![CD3217 (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
Detail all measurable or observable symptoms in this section.

- MacBook not turning on with and amp draw of ~0.23-0.31A at 5V with a USBC ammeter.
- Cycling or consistent amp draw on affected port.

## Solution
  - IMPORTANT:** If previous work was done on the board, an incompatible CD3217 might have been used. When replacing CD3217s, use a chip from an identical 820-01949 in the same format as it was on the donor board. New chips or chips from other models won't work, even if TBT ROMs are swapped.

### Diagnostic Steps
#### Check for DFU or Recovery Mode
- Connect the MacBook to another Mac via the master port and use Apple Configurator 2 to check for DFU mode.
- If in DFU mode, proceed to "Device stuck in DFU mode due to corrupt T2 firmware" repair steps.

#### Check Port Cycling and Amp Draw
- Check all 4 ports for cycling or different amp draws.
- If cycling occurs, a faulty CD3217 (Figure 1) may be tied to the specific port.
- CD3217 issues usually result in one port showing different readings, often cycling.

#### Inspect UB260 and Surrounding Area
- Visually inspect UB260 (Figure 2) and adjacent resistors and traces.
- Address any damage as necessary.![U3060 (Figure 3) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
![UB260 (Figure 2) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
#### Inspect U3060 and Surrounding Area:
- Visually inspect U3060 (Figure 3) and its surrounding resistors and traces.
- Address any damage as necessary.

### Repair Steps
#### Device stuck in DFU mode due to corrupt T2 firmware
- Revive or restore T2 firmware via Apple Configurator 2.
- Ensure you're running the latest macOS version for consistent results.
- [https://support.apple.com/guide/apple-configurator-mac/revive-or-restore-an-intel-based-mac-apdebea5be51/mac Follow the provided Apple support article for the procedure.]
- You should see a big square icon pop up that says "DFU" or rarely, "RECOVERY". Click the icon, Navigate to the top menu bar click "Actions" then "Advanced". Select Revive device. You will see a progress bar appear. This process can take anywhere from 2 minutes to over 30 minutes in some cases. It is important to note, if the device is in Recovery mode, the end user may have brought the device to another repair shop or Apple first, who attempted a DFU revive which failed. You may have a secondary issue if the revive fails again.
- **SELECTING RESTORE WILL WIPE ALL USER DATA!**
- Possible causes for a device to fail a DFU revive:
- # Short to ground on PP2v5_NAND_SSD_0
- # Absent U9000 voltages. (PP0v9_SSD_0, PPVCCQ_ANI_SSD0 (1.8v) )
- # Failed Trackpad (Will almost always show the Apple logo before failing the process.)
- # Failed NAND
- # Failed T2 or T2 RAM.
- # Cracked solder joints under T2 chip (Uncommon, usually only suspected if device was dropped prior to initial failure.)

#### Different ports are controlled by different CD3217s
- Left side bottom port: U3100_T
- Left side top port: U3100_X
- Right side bottom port: U3100_W
- Right side top port: U3100_R

#### For Liquid Damaged Boards
- Check for a short to ground on PP1v5_UPC_LDO_CORE and PP3v3_UPC around the CD3217 corresponding to the port showing different readings.
- If short is found, replace shorted component (could be a capacitor or CD3217).
- For a failed CD3217, consider reballing the chip tied to the problematic port.
- Inspect and replace corroded resistors as needed.
- Address visual delamination on CD3217 if present; it usually doesn't affect functionality.

#### For Non-Liquid Damaged Boards
- Check for a short to ground on PP1v5_UPC_LDO_CORE and PP3v3_UPC around the CD3217 linked to the port showing different readings.
- If short is identified, replace shorted component; otherwise, replace the CD3217 associated with the affected port.

#### Replacing CD3217s on the A2251/820-01949
- **IMPORTANT:** Use CD3217s from an identical 820-01949 donor board (RAM, CPU, and storage configurations do not matter).
- Chips must be replaced in the same order they were removed. U3100_T MUST BE USED TO REPLACE U3100_T AND SO ON. YOU CANNOT MIX THE CHIPS UP, IT WILL NOT WORK.
- Replacing or mixing up the chips with the wrong firmware may permanently corrupt the TBT ROMs!

If corrosion or trace damage is noticed near UB260 or U3060, replace corroded components, repair traces using jumper wires, and do not replace the chips. If the chip is corroded, clean pads and reuse the existing chip. Both ROMs have customized firmware. Replacement due to short or severe pad damage must be sourced from an identical 820-01949.
