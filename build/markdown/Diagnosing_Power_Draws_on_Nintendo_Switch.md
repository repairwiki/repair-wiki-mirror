---
title: "Diagnosing Power Draws on Nintendo Switch"
pageid: 692
revid: 4709
kind: explanatory_guide
source: "https://repair.wiki/w/Diagnosing_Power_Draws_on_Nintendo_Switch"
history: "https://repair.wiki/index.php?title=Diagnosing_Power_Draws_on_Nintendo_Switch&action=history"
permalink: "https://repair.wiki/index.php?oldid=4709"
last_edited: "2024-08-27T18:01:14Z"
contributors:
  - "ASRepairs"
  - "TechCentreUK"
  - "Aaron.stevenson408"
anonymous_edits: 1
categories:
  - "Explanatory guide"
  - "Explanatory guides for Nintendo Switch"
  - "Stubs"
infobox:
  Device: "Nintendo Switch"
  Type: "Troubleshooting/Diagnostics"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Diagnosing Power Draws on Nintendo Switch

## Introduction
Diagnosing power draws on the Nintendo Switch requires a systematic approach for accurate testing. In this guide, we'll perform diagnostics without a battery, bypassing the temp sensor using a 10k resistor. Using a bench power supply set to 4.2V at 2A, we'll test various components and check for specific power draws.
![Switch vsys.jpg](images/4/44/Switch_vsys.jpg)

## Symptoms
- No Display
- No Sound
- Incorrect Power Draw

## Diagnostic Steps
To find a solution to your specific power issue we need to follow a few steps to ensure we are testing correctly.

For this guide we will be testing without a battery and we will be bypassing the temp sensor by using a 10k resistor between the battery test pads next to the battery connector. Our bench power supply will be set to 4.2v at 2a (this is important as less than 2a will fail to reach second stage boot) and we will be powering via the VBAT test pad of the BQ24193 (Unless testing VSYS line for first stage boot).

  - First Stage Boot Checks** - **THIS IS THE ONLY TIME WE ARE USING VSYS INSTEAD OF VBAT**  Reduce amps to 1a, 4.2v on the VSYS line preferbly on the bottom side of the coil located next to BQ24193. If you have no short (max amps) then you are good to move forward and test the VCORE rails surrounding MAX77620 and the 3.3v regulator marked (EN--) above the audio ic. If you have short on the 3.3v rail move on and check M92T and P13USB etc. Next click and hold power button to turn on, watch the draw on bench power supply it should be around 195ma, but if you are getting the lower end of around 100-130ma then you could be looking at MAX77621 or MAX77812. If you have NO draw then you are most likely looking at MAX77620.

  - Fully Working Boot With LCD Connected** - Board will power up at 100ma which will then reach 150ma and hang for a small time, it will then jump to 500ma to 800ma.

  - Fully Working Boot Without LCD Connected** - Board will power up at 100ma which will then reach 150ma and hang for a small time, it will then jump to 400ma to 500ma.

  - Backlight Fault** - Board will power up at 100ma which will then reach 150ma and hang for a small time, it will then jump to 400ma to 500ma. This could be faulty backlight or backlight driver ( **TPS61163A** ).

  - Short** - Amps will max out on bench power supply, time to get to work with the multimeter, thermal cam or other methods. (I will provide another guide on most common areas for shorts)

  - M92T36** - Causes multiple issues when at fault but commonly a draw of 400ma - 800ma then a fast drop to 200ma and repeat. You can check capacitors surrounding M92T36 for shorts or alternatively can be removed along with P13USB and device will boot on bench power supply, If device now boots one of these are at fault.

  - P13USB** - Common for 300ma draw caused by USB port damage sending 15v to P13USB. When P13USB is at fault it will short the 3.3v rail causing 300ma on boot with no movement.

  - MAX77621** - Initial power up stopped by around 100ma where it will sit.

  - MAX17050** - If Fuel gauge or surrounding components are missing/damaged you will get a 100ma on boot and it will sit. Its known for creeping as high as 160ma and dropping back down to 120ma where it will sit. If you are getting a boot in a few seconds at 100-160ma most likely the MAX17050 will be at fault.

  - EMMC Fault** - 180 - 250ma but never entering second stage boot or getting a display is usually a great indicator of an emmc fault. sometimes a great way to test this is to plug into a payload injector and see if the device is in RCM / APX mode. This would be a great time to load up hekate an do some digging, First we need to check fuel gauge in the battery info tab and also run a benchmark on the emmc, i would advise you check auto RCM is switched off in case customer had switched it on. Next we will want to boot sysNand Atmosphere as some emmc corruption will be fixed by atmosphere. IF you are lucky enough to have a emuMMC backup and you can boot it, this is a great indicator that the second stage boot and MAX77620 is working, otherwise if you get a failed boot then MAX77620 can be a culprit. Moving on from these tests if you are finding that actually you do have a EMMC failure / corruption there is still a small hope we can clone the EMMC using "mmcblkNX" Nintendo switch emmc adapter and Linux. You can find more information on this [https://github.com/ignasurba/mmcblkNX here]. TO BE NOTED: Audio ic and wifi ic have also been known to show signs of a dead emmc / APX / RCM mode with the same boot draw.

Images to come.
