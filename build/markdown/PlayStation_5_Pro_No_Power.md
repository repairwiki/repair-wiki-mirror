---
title: "PlayStation 5 Pro No Power"
pageid: 6204
revid: 9549
kind: other
source: "https://repair.wiki/w/PlayStation_5_Pro_No_Power"
history: "https://repair.wiki/index.php?title=PlayStation_5_Pro_No_Power&action=history"
permalink: "https://repair.wiki/index.php?oldid=9549"
last_edited: "2025-07-30T22:26:45Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for PlayStation 5 Pro"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# PlayStation 5 Pro No Power

## Problem description
This guide will go over diagnosing the a PS5 Pro with no signs of life
![Standby Voltages](images/3/30/Ps5_pro_standby_voltages.jpg)

## Symptoms
- The device doesnt no turn on

## Solution
A Playstation 5 Pro that does not turn on can have many causes from a bad power supply to a motherboard problem.

### Diagnostic Steps
- The first thing to check is if the power supply is producing 12V, if 12V are not present this can be due to a faulty power supply or a short on the motherboard stopping the power supply from creating the 12V line.

![12V and 5V PS5 Pro](images/9/97/12V_and_5V_PS5_Pro.png)

- If 12V are present the next thing to check is if the 5V is present to do this check the voltage on the coil on the image bellow.

![12V and 5V PS5 Pro](images/9/97/12V_and_5V_PS5_Pro.png)

- If 5V is present the next thing to do is if the Southbridge IC is receiving the voltages need to work follow the image below and check if all these voltages are present.

![PS5 Southbridge PMIC Voltages](images/c/ce/PS5_Southbridge_PMIC_Voltages.png)

- If these voltages are all present the next thing to do is to make sure all the fuses on the motherboard are ok to do this look at the PCB there will be marking that start with FXXXX these are fuses with your multimeter in continuity mode check if there is continuity across.

- If all fuses are ok the next thing to check is for shorts on the motherboard especially on the capacitor on the backside of the Shoutbridge IC.

- If everything is the next thing thats left to do is to change the Southbridge IC sometimes they fail and wont be shorted.

## Repair Steps
If 12V are not present remove the PSU in diode mode measure the Positive side of the PSU terminal on the motherboard it should have a high reading between 0.400 and 0.500, if ok replace the PSU.

If you get a reading of 0.000 it means there is a short on the 12V check the [Short Circuits](Short_Circuits_-_Repair_Basics.md) page on a guide on how find the short.

If 5V is not present on the Motherboard this is probably due to a short on this line once again with your multimeter in diode mode measure the line and check if the value is high, it is common to have a short on the caps right next to the coil where you measured the 5V line.

If 1.15V and 3.3V on the image are missing it means that the PMIC is not working check if the 5V input is present if it is replace the PMIC, if 5V input is not present there is probably a short on this line if there is a short on the line F7002 will open.

The Southbridge IC is the same used on the PS5 Slim CXD90069GG so you can get one from a donor board or buy online from a reputable seller.
