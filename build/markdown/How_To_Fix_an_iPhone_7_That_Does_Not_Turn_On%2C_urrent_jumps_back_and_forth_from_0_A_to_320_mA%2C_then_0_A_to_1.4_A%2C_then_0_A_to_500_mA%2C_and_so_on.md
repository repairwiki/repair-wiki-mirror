---
title: "How To Fix an iPhone 7 That Does Not Turn On, urrent jumps back and forth from 0 A to 320 mA, then 0 A to 1.4 A, then 0 A to 500 mA, and so on"
pageid: 1425
revid: 3113
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_an_iPhone_7_That_Does_Not_Turn_On,_urrent_jumps_back_and_forth_from_0_A_to_320_mA,_then_0_A_to_1.4_A,_then_0_A_to_500_mA,_and_so_on"
history: "https://repair.wiki/index.php?title=How_To_Fix_an_iPhone_7_That_Does_Not_Turn_On,_urrent_jumps_back_and_forth_from_0_A_to_320_mA,_then_0_A_to_1.4_A,_then_0_A_to_500_mA,_and_so_on&action=history"
permalink: "https://repair.wiki/index.php?oldid=3113"
last_edited: "2024-01-20T20:57:53Z"
contributors:
  - "VCCBoardRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone 7"
  - "Repair guides for IPhone 7 Plus"
  - "Stubs"
infobox:
  Device: "IPhone 7, IPhone 7 Plus"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "BGA, Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix an iPhone 7 That Does Not Turn On, urrent jumps back and forth from 0 A to 320 mA, then 0 A to 1.4 A, then 0 A to 500 mA, and so on

## Problem description
No Power — After prompt to boot on DC power supply, current jumps back and forth from 0 A to 320 mA, then 0 A to 1.4 A, then 0 A to 500 mA, and so on
## Symptoms
- No current draw before prompt to boot on DC power supply
- After prompt to boot, you see the current jump quickly between 0 A and various values, like 0 A > 320 mA > 0 A > 1.4 A > 0 A > 500 mA

## Solution
### Diagnostic Steps
- Check for shorts around NAND
- Usually you'll find these lines with a shorted capacitor:
  - PP3V0_NAND
  - PP0V9_NAND
- If so, find the shorted capacitor by injecting voltage

  - Please note:** PMIC (U1801) will often show lots of heat if you're testing with the DCPS connected through the battery connector but it's not the cause of the short. The short is at the capacitor next to NAND, but since you're connected to the battery connector, the current has to flow through PMIC to get to the short cap, hence the PMIC heats up.

### Another Possible Cause:
![iPhone 7 Plus with SDRAM short](images/9/9a/IPhone_7_Plus_RAM_Short.jpg)
Sometimes, you'll see this same behavior when PP1V8_SDRAM or PP1V1_SDRAM is shorted. If this is the case, you'll need to check for heat above the CPU. If you find PP1V8_SDRAM or PP1V1_SDRAM is shorted and find heat above the CPU, then it's a RAM short.

You'll need to replace RAM to solve it. This a very advanced repair and should only be done by those who've mastered this repair. It's very easy for things to go wrong and damage the CPU.

### Repair Steps
Once you find the shorted capacitor, you can remove it and confirm the short is cleared.
