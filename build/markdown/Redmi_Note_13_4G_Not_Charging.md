---
title: "Redmi Note 13 4G Not Charging"
pageid: 4867
revid: 14187
kind: repair_guide
source: "https://repair.wiki/w/Redmi_Note_13_4G_Not_Charging"
history: "https://repair.wiki/index.php?title=Redmi_Note_13_4G_Not_Charging&action=history"
permalink: "https://repair.wiki/index.php?oldid=14187"
last_edited: "2026-03-21T20:20:41Z"
contributors:
  - "Ajimalg82"
  - "Hlyan Htet"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Redmi Note 13 4G"
  - "Stubs"
infobox:
  Device: "Redmi Note 13 4G"
  Affects_parts: "Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering, BGA"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Redmi Note 13 4G Not Charging

## Problem description
The device works fine, turn on and its fully functional but does not achrge at all and the charging is not even detected.
## Symptoms
- Phone works but does not charge.
- Turns on with new battery
- Diode value on main connector is ok
- Charging is not detected in on state or off state
- Draw on AMP meter is 0.000V

## Solution
Mainly this issue occurs with a faulty charger aur cable, in the result of this the device blows its OVP(Over Voltage Protection) ic to keep the device safe.

Note: Replacement of charger and charging cable is recommended after the repair.

### Diagnostic Steps
To check all the voltages you have to plugin only the charger, battery is not required to check the following voltages.

- Measure diode value on the charging FPC connector
- Check voltage on VBUS 5.0 volt
![Check VBUS](images/a/ad/INITIAL_CHECK.png)
- If 5.0 volt is present  on the VBUS line then proceed to check the following components
- Check if ovp ic is working:
  - Check the VBUS IN if is providing 5.0v
  - Check the VBUS OUT if its porviding the 5.0v output
![OVP IC FUNCTION](images/7/7a/MEASURE.png)
- If the VBUS OUT 5.0v is missing then proceed to the repair steps below.

### Repair Steps
- Remove the OVP IC
- Probe the pads to see there is no short to ground
- if everything is ok then proceed to make a jumper bypass the OVP IC from VBUS _ OVP _ INPUT   to  VBUS _ OVP _ OUTPUT
- (shown in the picture below)
![BYPASS OVP IC](images/3/37/BYPASS_OVP.png)
- Test if everything is working
- Apply solder mask and your device should be ready
![Solder mask applied](images/3/3f/Solder_mask_applied.jpg)
![Ready](images/a/a9/Ready.jpg)
