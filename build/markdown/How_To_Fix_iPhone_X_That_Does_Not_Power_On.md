---
title: "How To Fix iPhone X That Does Not Power On"
pageid: 1564
revid: 3402
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_iPhone_X_That_Does_Not_Power_On"
history: "https://repair.wiki/index.php?title=How_To_Fix_iPhone_X_That_Does_Not_Power_On&action=history"
permalink: "https://repair.wiki/index.php?oldid=3402"
last_edited: "2024-02-12T07:26:44Z"
contributors:
  - "VCCBoardRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone X"
  - "Stubs"
infobox:
  Device: "IPhone X"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "BGA, Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix iPhone X That Does Not Power On

## Problem description
Here's how to fix an iPhone X that does not power on. Does not boot up. Shows no signs of life. Just stays powered on.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- No Power
- Does not turn on
- Doesn't boot
- No signs of life
- Not booting
- Does not charge
- Pulls 2A or more beyond you prompt to boot
- No current draw before prompt to boot, but after prompt to boot, you see the current jump quickly between 0 A and various values, like 0 A > 320 mA > 0 A > 1.4 A > 0 A > 500 mA

## Solution
Do a full [visual inspection](visual_inspection.md) of the board and check for water damage under the stickers on the back. Remove the foam around the connectors to get a better look at everything. You're looking for any signs of corrosion on or around components and ICs.

If there is no water damage, it is most likely a shorted capacitor.

For iPhone X and newer models, you'll likely require the need to split the sandwich board. If you have no experience with sandwich splitting, please approach with caution. Doing it incorrectly can cause permanent damage.

### Short Before Prompt To Boot
Check the below lines:

- PP_VDD_MAIN — This is the most likely line to be shorted
- PP_VDD_BOOST — This line is usually shorted when it's not VDD MAIN
- PP_SPKRAMP_TOP_VBOOST — This is a bit rare but it does happen

You'll need to inject voltage (4 V / 2 A) directly into the line you measured as short and use freeze spray or thermal camera to spot the capacitor that is shorted.

In these cases, you can just remove the shorted capacitor and not replace it. The device will function normally with no negative effects.

Replacing it means you are adding more heat to the board to reinstall it, which increases the risk of something going wrong.

If you have a case of water damage, then you'll have to pay attention to the spots on the board where there are signs of water damage.

Often, you'll find corrosion on capacitors but also under IC

You'll need to visually inspect these areas to see if they're liquid damaged

Please Note: If you are using a DC power supply to inject voltage through the battery connector, like using an iPower Pro or DT880, be aware that the Tigris Mosfet Q3350 will heat up instantly. This is because the battery connector line PP_BATT_VCC connects to PP_VDD_MAIN through it, which creates lots of heat. Q3350 itself does not have a connection to ground, therefore, it's impossible for it to be shorted.

### Short After Prompt To Boot
- Check for shorts around NAND
- Usually you'll find these lines with a shorted capacitor:
  - PP3V0_NAND
  - PP0V9_NAND
  - PP1v8_IO
- If so, find the shorted capacitor by injecting voltage

Please note: PMIC (U2700) will often show lots of heat if you're testing with the DCPS connected through the battery connector but it's not the cause of the short. The short is at the capacitor next to NAND, but since you're connected to the battery connector, the current has to flow through PMIC to get to the short cap, hence the PMIC heats up.

Another Possible Cause:

Sometimes, you'll see this same behavior when PP1V8_S2 or PP1V1_S2 is shorted. If this is the case, you'll need to check for heat above the CPU. If you find PP1V8_S2 or PP1V1_S2 is shorted and find heat above the CPU, then it's a RAM short.

You'll need to replace RAM to solve it. This a very advanced repair and should only be done by those who've mastered this repair. It's very easy for things to go wrong and damage the CPU.
