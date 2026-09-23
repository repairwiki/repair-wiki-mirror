---
title: "MacBook Pro A2141 Not turning on, drawing 0.10-0.15A at 20V repair"
pageid: 108
revid: 509
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A2141_Not_turning_on,_drawing_0.10-0.15A_at_20V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A2141_Not_turning_on,_drawing_0.10-0.15A_at_20V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=509"
last_edited: "2023-10-29T15:27:29Z"
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

# MacBook Pro A2141 Not turning on, drawing 0.10-0.15A at 20V repair

## Problem description
Possible Diagnoses for a 820-01700 with 20v on the charger and 0.10-0.15a as measured by a USB-C amp meter
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- MacBook not turning on/powering on
- All voltages are missing
- Drawing only 0.1 to 0.15 A at 20V

## Solution
### Diagnostic Steps
#### Measure for a short on PP2v5_NAND_SSD0 and PP2v5_NAND_SSD1
  - Relevant diode mode measurements:**

PP2v5_NAND_SSD1: ~0.400-0.500

PP2v5_NAND_SSD0: ~0.400-0.500

- With multimeter on resistance mode
  - Place your black probe on ground point and red probe on one of those rails
  - if you read less than 50 Ohms then you have a short here

### Repair Steps
#### Short on PP2v5_NAND_SSD0 or PP2v5_NAND_SSD1
- If a short to ground is found, check U9080 and U9580 for signs of corrosion or burn marks.
  - Often times you will find U9080/U9085 will have a "shadow" over a portion of the chip if it is bad. If this is seen, remeasure the line.
    - If resistance/diode mode readings return to normal limits, replace the failed IC.
    - If U9580 or U9080 is the cause of the short, be sure to check their relevant 2v5 power rails for shorts to ground.
    - If you find one of the PP2v5_NAND_SSD lines reading 1-3 ohms to ground, the NAND chips are likely dead and the board is not practically repairable.
    - If both PP2v5_NAND_SSD lines are within normal resistance and diode mode readings (See above) and the board still does not turn on, and displays a amp reading of 0.03-0.06, check to see if it is in recovery mode with Apple Configurator 2 and [https://support.apple.com/guide/apple-configurator-mac/revive-or-restore-an-intel-based-mac-apdebea5be51/mac revive as necessary].
      - *Once plugged in, open Apple Configurator 2. You should see a big square icon pop up that says "DFU" or rarely, "RECOVERY". Click the icon, Navigate to the top menu bar click "Actions" then "Advanced". Select Revive device. You will see a progress bar appear. This process can take anywhere from 2 minutes to over 30 minutes in some cases.* *It is important to note, if the device is in Recovery mode, the end user may have brought the device to another repair shop or Apple first, who attempted a DFU revive which failed. You may have a secondary issue if the revive fails again.*
- If U9080 and U9580 look good, inspect the capacitors on this line as they are commonly corroded due to dust.
  - C9088, C9087, C9588 and C9586 are common culprits on this board.
