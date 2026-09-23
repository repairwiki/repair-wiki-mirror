---
title: "IPhone 12 Stuck In Recovery Mode After Water Damage Solution"
pageid: 285
revid: 735
kind: repair_guide
source: "https://repair.wiki/w/IPhone_12_Stuck_In_Recovery_Mode_After_Water_Damage_Solution"
history: "https://repair.wiki/index.php?title=IPhone_12_Stuck_In_Recovery_Mode_After_Water_Damage_Solution&action=history"
permalink: "https://repair.wiki/index.php?oldid=735"
last_edited: "2023-11-05T22:21:16Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone 12"
  - "Repair guides for iPhone 12 Pro"
  - "Repair guides for iPhone 12 Pro Max"
infobox:
  Device: "IPhone 12, iPhone 12 Pro, iPhone 12 Pro Max"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 12 Stuck In Recovery Mode After Water Damage Solution

## Problem description
A common problem on iPhone 12, 12 Pro and 12 Pro Max after water damage near the power button connector is that it will be stuck in either Recovery Mode or Diagnostics Mode.

When you flash an update (or restore) and see that it flashes successfully. But then goes right back to recovery mode.

Essentially the issue is caused by water damage. It will somehow damage the PMIC, preventing it from outputting the 1.8V required on the power button/vol button lines to be in the "non-pressed" state.

When a line is measuring low voltage, electrically, the circuit thinks the button is being pressed. In this case, the damaged PMIC is mimicking a constant press due to the lack of the 1.8V at that line. So this is why it's stuck in Recovery Mode or Diagnostics Mode, as those mode require you to boot the phone while holding down their respective buttons.

Please note:

If data recovery is important, this issue needs to be fixed so the phone can boot & access data. So do NOT restore the phone if you're seeing this issue. Updates will be fine with no chance of data loss.

## Symptoms
The symptoms will be

- Water damage or corrosion around the power button connector on the motherboard
- Device is stuck in recovery mode, even with power button flex unplugged
  - An update will complete 100% success, but will return back to recovery mode on its own
- Device in stuck in Diagnostic Mode
![iPhone 12 Pro Max Power Button Connector with Water Damage](images/7/76/IPhone_12_Pro_Max_Power_Button_Connector_with_Water_Damage.png)

## Solution
### Diagnostic Steps
First, you want to check the power button connector for liquid damage. Signs of corrosion will be your first clue. Clean all that off with isopropyl alcohol & a toothbrush.

Then boot the phone with a DC Power Supply (or in a known good housing) & measure **IO_BUTTON_SIDE_L_1V8_CONN** for voltage. You want to measure for **1.8V. while the phone is booted.**

If you get something like 0.6V, then you most likely have an issue with PMIC.

Also, measure the volume button lines for 1.8V.

- **IO_BUTTON_VOL_DOWN_L_1V8_CONN**
- **IO_BUTTON_VOL_UP_L_1V8_CONN**

If you get a lower voltage, like 0.6V, then you have issue with PMIC.

### Repair Steps
You basically have 2 options. Easy option or difficult option.  The easy option should be considered only for Data Recovery.

1. Easy - Run a jumper from PP1V8_S2 to the lines stuck on a LOW state. So if you measured **IO_BUTTON_SIDE_L_1V8_CONN** was stuck on 0.6V (instead of 1.8V), you can feed it the 1.8V it is expecting. Same for the volume button lines. (see example image below)![iPhone12PM Jumper Solution for Stuck In Recovery Mode. PP1V8_S2 is feeding the 1.8V into the lines stuck on LOW. So the phone will stop being stuck in recovery mode.](images/2/21/IPhone12PM_Jumper_Solution_for_Stuck_In_Recovery_Mode.png)
1. Hard - Replace PMIC, which requires splitting the 2 layer motherboard sandwich.
