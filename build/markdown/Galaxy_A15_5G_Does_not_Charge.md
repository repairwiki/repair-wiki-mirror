---
title: "Galaxy A15 5G Does not Charge"
pageid: 7804
revid: 11535
kind: repair_guide
source: "https://repair.wiki/w/Galaxy_A15_5G_Does_not_Charge"
history: "https://repair.wiki/index.php?title=Galaxy_A15_5G_Does_not_Charge&action=history"
permalink: "https://repair.wiki/index.php?oldid=11535"
last_edited: "2025-09-13T21:10:47Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Galaxy A15 5G"
  - "Stubs"
infobox:
  Device: "Galaxy A15 5G"
  Affects_parts: "Motherboard"
  Needs_equipment: "Soldering Iron, Hot-Air Station, Microscope"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Galaxy A15 5G Does not Charge

## Problem description
The device does not Charge
## Symptoms
- Device doesn't charge.

## Solution
There isn't a straight solution to fix a Galaxy A15 not charging however in this guide we will go over how the charging circuit works.

### Diagnostic Steps
The first thing is if you can try a new charge port and Flex cable and if you have on hand a battery as well, you don't have a board problem until you prove you dont have a parts problem.

If parts dont fix the issue the problem is on the motherboard.

The first thing to check is for any damage to this FPC, it is super common to have this FPC damaged especially if the phone is bent.

if the FPC is damage the Solution is to replace it, this FPC is the same on all these devices: **Galaxy A52 / 5G (A525 / A526 / 2021) / A32 / 5G (A325 / A326 / 2021) / A42 5G / A12 / A53 5G / A54 5G / A15 5G / A72 / A13 5G / A23 5G**
![Galaxy A15 FPC](images/3/3a/Galaxy_A15_FPC.png)
If the FPC is ok next thing to do is making sure the board is receiving 5V from the charger.

To mesure this like you need to connect the charger to the Phone.
![5V input](images/e/e6/5V_input.png)
If 5V are not present and you have made sure that the charge and Flex cable are ok there may be a short on this line or a broken connection between the motherboard layers.

Next step if the 5V are present is to check if the Over Voltage protection IC is letting the current trough.

Check that you have 5V in the spot like in the image below if you don't the OVP is letting the voltage trough replace it.
![Galaxy A15 OVP](images/a/a5/Galaxy_A15_OVP.png)

Next thing to check is if the the IF PMIC is getting the 5V if you dont have 5V on point in the image below replace the SM5461 IC
![IF PMIC 5V input](images/8/8d/IF_PMIC_5V_input.png)

If 5V are present there Replace the IF PMIC SM5714A this is the actual chip that charges the battery.

If even after doing all these steps the device does not charge check the CC1 and CC2 lines Check lines connect to the IF PMIC the expected diode value of them is 0.660

These lines can be measured here:
![Galaxy A15 CC Lines](images/4/44/Galaxy_A15_CC_Lines.png)

These steps should cover all issues all issues related to charging of the Galaxy A15 the most common issues are a damaged FPC, a Faulty or Blow OVP, or a faulty IF PMIC.

## Final Testing
If you replaced the FPC, make sure to test every function of the device, especially:

- Bottom Speaker
- Bottom mic
- Data transfer
- Image/touch

If the OVP was faulty, try to understand if the previous cable/charger is of good quality.
