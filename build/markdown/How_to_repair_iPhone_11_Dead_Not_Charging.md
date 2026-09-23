---
title: "How to repair iPhone 11 Dead Not Charging"
pageid: 7352
revid: 10915
kind: repair_guide
source: "https://repair.wiki/w/How_to_repair_iPhone_11_Dead_Not_Charging"
history: "https://repair.wiki/index.php?title=How_to_repair_iPhone_11_Dead_Not_Charging&action=history"
permalink: "https://repair.wiki/index.php?oldid=10915"
last_edited: "2025-08-30T10:54:34Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 11"
infobox:
  Device: "iPhone 11"
  Affects_parts: "Logic Board, CPU"
  Needs_equipment: "Microscope, Hot air station, Soldering iron"
  Difficulty: "4. Specialist"
  Type: "Soldering"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How to repair iPhone 11 Dead Not Charging

  - Note**: This repair should only be performed for data recovery purposes. The procedure is extremely delicate and not recommended for long-term use. Once the CPU is reballed and reinstalled, the factory underfill (glue) beneath the CPU will no longer be present, making the device far more vulnerable to damage. Even a minor drop or flex on the board can result in further failures or a complete loss of functionality. Proceed with caution and do not guarantee reliability beyond successful data extraction.

## Problem description
![iPhone 11 behavior after prompt to boot on DCPS](images/b/ba/Iphone11_cpu_issue.gif)
The iPhone 11 is prone to cold solder issues under the CPU, often caused by:

- Long-term heating/cooling cycles (thermal stress)
- Drops or board flexing
- Manufacturing weakness in solder joints

This results in the CPU losing contact intermittently with the logic board.

## Symptoms
- Phone does not power on.
- On DC power supply: after prompt to boot, current rises to 0.140–0.150 A and gets stuck.
- Device  boots if you split the logic board (lower and upper layer), confirming CPU connection issue.
- Issue recurs unless CPU is reballed.

## Diagnostic Steps
1. Connect the phone to a DC power supply. Observe current behavior → prompt to boot → stalls at ~0.140–0.150 A.
1. Split the logic board. If the device boots normally with the layers separated, suspect cold solder under CPU.
1. Confirm by reassembling → device will fall back into the same stuck state eventually.![CPU successfully removed from board for reball](images/9/9d/Cpu_lifted_from_board.png)

## Repair Steps
1. Remove the logic board and split the layers.
1. Inspect CPU solder balls under microscope (signs of cracked/cold joints may be visible).
1. Reball the CPU: Carefully remove residual solder from pads. Apply fresh solder balls with proper stencil. Reflow CPU with controlled temperature profile.
1. Reassemble the board layers and reinstall CPU.
1. Test on DC power supply → device should now boot normally.![iPhone 11 booted successfully, after recalling CPU](images/5/59/Success_boot_11.png)
