---
title: "MacBook Pro A2141 Not turning on, stuck in recovery mode drawing 0.060A at 20V repair"
pageid: 9092
revid: 13193
kind: other
source: "https://repair.wiki/w/MacBook_Pro_A2141_Not_turning_on,_stuck_in_recovery_mode_drawing_0.060A_at_20V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A2141_Not_turning_on,_stuck_in_recovery_mode_drawing_0.060A_at_20V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=13193"
last_edited: "2025-12-11T09:07:26Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A2141"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A2141 Not turning on, stuck in recovery mode drawing 0.060A at 20V repair

![A2141 Error 6 (Figure 1) -- MacBook Pro A2141 Error Code 6 while reviving in Apple Configurator 2](images/4/45/Error-6-a2141.png)

## Problem description
MacBook Pro A2141 comes in dead.

When connected to USB-C power meter or DCPS, machine negotiates:

- 20 V @ 0.60 A (steady, no boot current spike)

Attempting to boot leads only to Recovery Mode or DFU mode.

A Revive attempt using Apple Configurator 2 fails with:

- Error 6  (See fig. 1)

Error 6 on T2  Macs commonly corresponds to:

- Missing NAND power rails
- NAND not responding
- SSD voltage regulators defective
- NAND line short or partial short

![A2141 TPS62180  (Figure 2) -- MacBook Pro A2141 TPS62180 (U9080) SSD NAND Regulator IC on logic board](images/b/b5/A2141_tps_board.png)

## Symptoms
- Device does not boot macOS
- Stuck in Recovery / DFU
- No progress during revive
- Apple Configurator stops early in process
- Error 6 returned consistently
- No SSD activity

## Solution
![A2141 TPS62180  (Figure 3) -- MacBook Pro A2141  TPS62180 (U9080) SSD NAND Regulator IC on board view software](images/c/c7/A2141_tps_boardview.png)

### Diagnostic Steps
![A2141 Booted (Figure 3) -- MacBook Pro A2141 Successfully booted up after fixing missing NAND voltage and reviving in Apple Configurator 2](images/0/07/A2141-bootup-after-revive.png)

#### 1. USB-C Power Negotiation
- 20 V, ~ 0.60 A = device is alive at PMIC level but not booting OS
- No secondary current spikes → SSD, T2, or SMC sequencing failure

#### 2. Enter DFU / Recovery
Device recognized by Apple Configurator → confirms T2 not booting fully.

#### 3. Attempt Revive
Fail: Error 6 → strongly indicates storage subsystem / NAND power fault.

#### 4. Check SSD Rails
Probe SSD rails:

- 2V5_SSD0 = present
- 2V5_SDD1 = missing
- 1V8_SSD0 = present
- 1V8_SSD1 = present
- 0V9_SSD = present
- Mild short detected to ground (partial) on 2V5_SDD1 line

#### 5. Thermal / Voltage Injection
Inject low voltage (1.00V @ 5.00A)→ TPS62180 heats quickly → confirmed culprit.

### Repair Steps
#### 1. Remove TPS62180
- Mask surrounding components
- Preheat board
- Lift IC cleanly
- Re-test short: rail now normal

#### 2. Install New TPS62180
- Clean pads
- Tin pads + apply flux
- Reflow new IC
- Verify solder joints under microscope

#### 3. Re-check 2V5_SSD1
- Rail now present and stable at ~2.5 V
- No more short
- SSD communication restored

#### 4. Reattempt Revive (Not Restore!)
Using Apple Configurator 2:

- Device enters DFU
- Start Revive
- This time process completes successfully
- macOS boots normally
- User data preserved

## NOTE:
#### Always choose “Revive” first if data is important.
- Revive
  - Rebuilds firmware & bridgeOS
  - Preserves user data
  - Repairs firmware corruption
- Restore
  - Erases NANDs
  - Re-installs macOS
  - All data lost
