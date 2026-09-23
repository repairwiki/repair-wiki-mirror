---
title: "MacBook Pro A2141 Not turning on, ~0.23-0.31A current draw at 5V repair"
pageid: 105
revid: 510
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A2141_Not_turning_on,_~0.23-0.31A_current_draw_at_5V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A2141_Not_turning_on,_~0.23-0.31A_current_draw_at_5V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=510"
last_edited: "2023-10-29T15:27:33Z"
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
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A2141 Not turning on, ~0.23-0.31A current draw at 5V repair

## Problem description
No Power, 5v and ~0.23-0.31A, Cycling or not cycling on the 820-01700 logic board diagnosis and repair.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- MacBook not turning on
- No voltages are present
- Only drawing 0.23-0.31A current at 5V when measured with USB-C meter.

## Solution
### Diagnostic Steps
#### Check for DFU or Recovery Mode
- Connect the MacBook Pro A2141 to another Mac or MacBook via the master port (bottom left side USB-C port, closest to the display).
- Use Apple Configurator 2 to verify whether the device is in DFU or recovery mode.
- If the device is in DFU mode, proceed to "Device stuck in DFU mode due to corrupt firmware" in the repair steps below.

#### Check all  ports, CD3217 issue
- See whether one port cycles or has a different amp draw.
- In the presence of CD3217 issues, you will almost always find one port reading differently; with the most common finding being cycling.

#### Visually inspect TBT ROMs (U2890 and UB090) for corrosion
If corroded, TBT ROMs usually do not have to be replaced. Lift, and clean pads if necessary and replace any corroded resistors. Run jumpers as needed.

### Repair Steps
#### Device stuck in DFU mode due to corrupt firmware
- Revive firmware via Apple Configurator 2.
- Ensure the MacBook is running the latest macOS version for consistent results. Check for MacOS updates prior to reviving/restoring T2 firmware.
- [https://support.apple.com/guide/apple-configurator-mac/revive-or-restore-an-intel-based-mac-apdebea5be51/mac Follow the provided Apple support article for the procedure.]
  - Plug the device you are working on to another Mac or MacBook via its master port. The master port on the A2141 is the bottom left side USB-C port (closest to the trackpad).
  - Once plugged in, open Apple Configurator 2. You should see a big square icon pop up that says "DFU" or rarely, "RECOVERY".
  - Click the icon, Navigate to the top menu bar click "Actions" then "Advanced".
  - Select Revive device. You will see a progress bar appear. This process can take over 30 minutes in some cases.
  - Be cautious that selecting "Restore" will wipe all user data.
- Possible causes for a device to fail a DFU revive include various hardware issues.

#### CD3217 issue
- If one port cycles, or has a different amp draw than the others, the offending CD3217 is likely tied to this port.
    - LEFT SIDE BOTTOM PORT IS CONTROLLED BY U3200*
    - LEFT SIDE TOP PORT IS CONTROLLED BY U3100*
    - RIGHT SIDE BOTTOM PORT IS CONTROLLED BY UB300*
    - RIGHT SIDE TOP PORT IS CONTROLLED BY UB400*
- If liquid damage is suspected, Check PP1v5_UPC_LDO_CORE and PP3v3_UPC_LDO for shorts to ground around the CD3217 of the port that is displaying different readings than the rest.
- #If a short to ground is identified, remove and replace the corresponding component, which may be a capacitor or the CD3217 itself.
- #If the CD3217 is found to be faulty, replace the chip associated with the port in question.
- #***YOU MUST SOURCE THE REPLACEMENT CD3217 FROM ANOTHER 820-01700 DONOR BOARD**
- #Heat-induced delamination of the CD3217 is commonly observed, yet this typically does not affect the functionality or longevity of the IC.
- #All surrounding resistors should be inspected for corrosion and replaced if necessary.
- #Lastly, pad damage should be examined for, particularly on lines fed by 3.3v, as this can often be overlooked and mimic a CD3217 issue.
- If there is no liquid damage, investigate a potential short to ground on PP1v5_UPC_LDO and PP3v3_UPC_LDO around the CD3217 corresponding to the port that is reading differently from the others.
  - If a short to ground is found, remove and replace the component causing the short
  - If no short is found, replace the CD3217 connected to the malfunctioning port.
