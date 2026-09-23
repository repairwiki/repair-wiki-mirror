---
title: "IPhone XR Stuck in DFU, updates successfully but goes back to DFU"
pageid: 3739
revid: 13813
kind: repair_guide
source: "https://repair.wiki/w/IPhone_XR_Stuck_in_DFU,_updates_successfully_but_goes_back_to_DFU"
history: "https://repair.wiki/index.php?title=IPhone_XR_Stuck_in_DFU,_updates_successfully_but_goes_back_to_DFU&action=history"
permalink: "https://repair.wiki/index.php?oldid=13813"
last_edited: "2026-02-02T00:08:04Z"
contributors:
  - "VCCBoardRepairs"
  - "Samhext"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone XR"
  - "Stubs"
infobox:
  Device: "IPhone XR"
  Affects_parts: "Motherboard"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone XR Stuck in DFU, updates successfully but goes back to DFU

## Problem description
Stuck in DFU mode

Flashes successfully with an update or restore but goes back to DFU mode.
![iPhone XR R0601 DFU Resistor. If broken, it will cause the phone to be stuck in DFU mode](images/b/be/IPhone_XR_R0601_DFU_Resistor.png)

## Symptoms
- Screen shows no image and pulls 0.45A via USB charging
- Does not appear to boot
- Prompt to boot on DCPS, shows it hangs around 45mA draw
- Connect to PC and it's in DFU mode
- Flash an update or restore & it goes through 100% with no errors but goes back to DFU mode

## Solution
- Check R0601 at the corner of NAND.
- This resistor connects PP1V8_IO to SPI_AP_TO_S4E_MOSI_BOOT_CONFIG1
- Clean the underfill around it & poke it hard.
- If it breaks, it must be replaced.
- Value is 4.7ohms
- After replacing it, the phone will no longer be in DFU mode & boot right up.

Migrated from old wiki
