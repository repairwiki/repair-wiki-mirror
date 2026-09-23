---
title: "PlayStation 5 Fan not working"
pageid: 8687
revid: 12631
kind: other
source: "https://repair.wiki/w/PlayStation_5_Fan_not_working"
history: "https://repair.wiki/index.php?title=PlayStation_5_Fan_not_working&action=history"
permalink: "https://repair.wiki/index.php?oldid=12631"
last_edited: "2025-11-09T22:33:03Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for PlayStation 5"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# PlayStation 5 Fan not working

## Problem description
The console turns on but the Fan does not spin
![Example of a ripped FAN FPC](images/9/95/Ripped_fan_fpc_ps5.jpg)

## Symptoms
- The Fan doesn't spin

## Solution
The first thing to try is a new fan, as it is common for the PS5 fan to die.

If, with a new fan, the fan still does not spin, the issue is on the motherboard.

This can be something simple like a damaged fan FPC (a common issue) or a faulty Southbridge.

If there is no physical damage to the FPC, the next thing to do is to take diode readings of the fan FPC and compare them with the image below.
![PS5 Fan FPC.png](images/8/8f/PS5_Fan_FPC.png)
Since the console turns on, 12V is present, as the fan uses the main 12V line for power. Without this line, the console would not turn on.

If you get no reading at all on the PWM signal, the cause can be a crack in the PCB layer, a bad solder ball under the Southbridge IC, or a faulty Southbridge IC.

The fan PWM signal comes directly from the Southbridge CXD90061GG or CXD90069GG.
![PS5 PWM Signal](images/7/71/PS5_PWM_Signal_.png)
If there is a short on this line the Southbridge must be replaced.
![PWM signal pad under the southbridge](images/2/28/PWM_signal_pad_under_the_southbridge.png)

### Repair Steps
If a new fan works well, all that's needed is to replace the fan.

If the FPC is ripped off the board, you must solder a new one. It is common to have the anchor points of the FPC ripped off the board. The best way to fix it is to use solder wick to make a base. You can follow this video made by [https://youtu.be/R1JG9Jit2do?si=1t8ZtM6K-3ceCXM5 Uber Micro Repair]

If the Southbridge needs to be replaced: Remove the CMOS battery from the board.

Use your hot air station without a nozzle to desolder the old Southbridge (It is recommended to use a board preheater).

While the board is hot, clean the pads of the motherboard; be gentle to not damage any or scrape the PCB mask.

Currently, there are 2 types of Southbridge available for the PS5: CXD90061GG and CXD90069GG.

When installing a new one, you have to match them (There is a way to install a 61GG on a 69GG, but that won’t be covered in this guide).

Usually, the Southbridges that you buy online come reballed, so solder the new chip in place.

After soldering the new IC, do your best to try and clean the flux from under the chip. Install the CMOS battery once the board is cold.

## Final Testing
If the Fan or FPC was repaired boot up a game and see if the fan is working as expected.

If the Southbridge was replaced try and test every function of the console.
