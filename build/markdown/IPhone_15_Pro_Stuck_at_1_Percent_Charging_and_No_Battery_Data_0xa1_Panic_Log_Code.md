---
title: "IPhone 15 Pro Stuck at 1 Percent Charging and No Battery Data 0xa1 Panic Log Code"
pageid: 4305
revid: 7350
kind: repair_guide
source: "https://repair.wiki/w/IPhone_15_Pro_Stuck_at_1_Percent_Charging_and_No_Battery_Data_0xa1_Panic_Log_Code"
history: "https://repair.wiki/index.php?title=IPhone_15_Pro_Stuck_at_1_Percent_Charging_and_No_Battery_Data_0xa1_Panic_Log_Code&action=history"
permalink: "https://repair.wiki/index.php?oldid=7350"
last_edited: "2025-06-04T21:18:23Z"
contributors:
  - "VCCBoardRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone 15 Pro"
  - "Repair guides for IPhone 15 Pro Max"
  - "Stubs"
infobox:
  Device: "IPhone 15 Pro, IPhone 15 Pro Max"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering, BGA"
  Difficulty: "4. Specialist"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 15 Pro Stuck at 1 Percent Charging and No Battery Data 0xa1 Panic Log Code

## Problem description
iPhone 15 Pro that is not charging. It says it is at 1% battery level & doesn't go up. The USB meter is constantly fluctuating. When you plug in the charging cable, it pops up as 0% remaining.

It also restarts every 3 minutes due to lack of battery data. The panic log error will be 0xa1.

Even with a new battery and charging port installed, the symptoms will remain the same.

This tends to happen when the phone gets water damaged & fries the PMIC.
![Figure 1 - iPhone 15 Pro 0xa1 Panic Log Example](images/6/6b/15_Pro_0xa1_Panic_Log.png)

## Symptoms
- Not Charging at 9V
- USB Meter is fluctuating
- Always reads battery at 1%
- When plugging in the charger, it says 0% remaining
- Restarts every 3 minutes
- Panic Log Error code is 0xa1 (Figure 1)

## Solution
### Diagnostic Steps
1. Test with known good parts. Specifically battery & charging port
1. Check the battery connector for damage. The pins should all be straight & not bent, warped or missing
1. Check the connector **Diode Mode Values**:
  1. ZXW Pin 1: 0.439V
    1. I2C2_SMC_CHARGER_BI_GG_SDA_1V8
  1. ZXW Pin 2: 0.548
    1. I2C2_SMC_CHARGER_TO_GG_SCL_1V8_CONN
  1. ZXW Pin 5: OL
    1. ANALOG_BATT_VCELL_NEG_CONN
  1. ZXW Pin 6: 0.505V
    1. ANALOG_BATT_VCELL_POS_CONN ![iPhone 15 Pro FPC Connector Diode Mode Values](images/4/40/IPhone_15_Pro_FPC_Connector_Diode_Mode_Values.png)
1. Check the **voltage** of the battery connector pins, by connecting the board only, with charging port flex. Then plug in the charger to it & measure each pin:
  1. ZXW Pin 1: 1.5V
    1. I2C2_SMC_CHARGER_BI_GG_SDA_1V8
  1. ZXW Pin 2: 1.8V
    1. I2C2_SMC_CHARGER_TO_GG_SCL_1V8_CONN
  1. ZXW Pin 5: 0.6V
    1. ANALOG_BATT_VCELL_NEG_CONN
  1. ZXW Pin 6: 0.6V
    1. eANALOG_BATT_VCELL_POS_CONN![iPhone 15 Pro Board & Charging Port. How to measure the voltage at the battery connector](images/4/4f/IPhone_15_Pro_Board_&_Charging_Port.png)

### Repair Steps
If you have a bad diode mode reading or low voltage on the battery connector, it's likely PMIC that has failed.
