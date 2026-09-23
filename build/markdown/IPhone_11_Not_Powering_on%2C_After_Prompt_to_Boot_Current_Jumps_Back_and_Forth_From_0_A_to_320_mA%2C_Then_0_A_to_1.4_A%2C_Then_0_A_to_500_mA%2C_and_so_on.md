---
title: "IPhone 11 Not Powering on, After Prompt to Boot Current Jumps Back and Forth From 0 A to 320 mA, Then 0 A to 1.4 A, Then 0 A to 500 mA, and so on"
pageid: 4599
revid: 7668
kind: repair_guide
source: "https://repair.wiki/w/IPhone_11_Not_Powering_on,_After_Prompt_to_Boot_Current_Jumps_Back_and_Forth_From_0_A_to_320_mA,_Then_0_A_to_1.4_A,_Then_0_A_to_500_mA,_and_so_on"
history: "https://repair.wiki/index.php?title=IPhone_11_Not_Powering_on,_After_Prompt_to_Boot_Current_Jumps_Back_and_Forth_From_0_A_to_320_mA,_Then_0_A_to_1.4_A,_Then_0_A_to_500_mA,_and_so_on&action=history"
permalink: "https://repair.wiki/index.php?oldid=7668"
last_edited: "2025-06-14T00:28:47Z"
contributors:
  - "Samhext"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 11"
  - "Stubs"
infobox:
  Device: "iPhone 11"
  Affects_parts: "Main Logic Board"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 11 Not Powering on, After Prompt to Boot Current Jumps Back and Forth From 0 A to 320 mA, Then 0 A to 1.4 A, Then 0 A to 500 mA, and so on

![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- No current draw before prompt to boot on DC power supply
- After prompt to boot, you see the current jump quickly between 0 A and various values, like 0 A > 320 mA > 0 A > 1.4 A > 0 A > 500 mA

## Solution
- Check for shorts around NAND
- Usually you'll find these lines with a shorted capacitor:
  - PP2V63_NAND
  - PP1V8_NAND
  - PP0V9_NAND
- If so, find the shorted capacitor by injecting voltage

Here's a video tutorial of an iPhone 11 Pro with this same issue. It would be the same for iPhone 11: https://youtu.be/1sboZLnURIc

  - Please note:** PMIC (U1801) will often show lots of heat if you're testing with the DCPS connected through the battery connector but it's not the cause of the short. The short is at the capacitor next to NAND, but since you're connected to the battery connector, the current has to flow through PMIC to get to the short cap, hence the PMIC heats up.

- Migrated from old wiki*
