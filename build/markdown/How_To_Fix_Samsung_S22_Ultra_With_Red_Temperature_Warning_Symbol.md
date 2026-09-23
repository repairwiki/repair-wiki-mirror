---
title: "How To Fix Samsung S22 Ultra With Red Temperature Warning Symbol"
pageid: 1710
revid: 4970
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_Samsung_S22_Ultra_With_Red_Temperature_Warning_Symbol"
history: "https://repair.wiki/index.php?title=How_To_Fix_Samsung_S22_Ultra_With_Red_Temperature_Warning_Symbol&action=history"
permalink: "https://repair.wiki/index.php?oldid=4970"
last_edited: "2024-10-07T07:06:52Z"
contributors:
  - "ASRepairs"
  - "VCCBoardRepairs"
  - "Malqamri77"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Galaxy S22 Ultra"
infobox:
  Device: "Galaxy S22 Ultra"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "BGA, Soldering"
  Difficulty: "4. Specialist"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix Samsung S22 Ultra With Red Temperature Warning Symbol

## Problem description
Samsung S22 Ultra has a common fault where it will give you a red exclamation mark warning when you plug in the charger.

If the device boots, it will say it's either very hot or very cold & it cannot charge & will shut down. This can happen out of nowhere.
S22 Ultra also does not require the wireless coil/back cover to prevent the temp warning, like some of the older models do. A fully working S22 Ultra will charge fine without the wireless coil/back cover.
![Samsung S22 Ultra with a temperature warning when charging](images/7/79/S22_ultra_temp_warning.png)
This issue lies within the motherboard itself
## Symptoms
- Does not charge
- Show red exclamation mark error message

## Solution
### Diagnostic Steps
![Samsung S22 Ultra - Connector Temp Sensor Line that you must check for a short.](images/a/a2/S22_Ultra_Connector_Temp_Sensor_Line.png)
Check the 3rd pin form the top right of the charging port FPC (SOC25000). The line is called USB_THM (USB Thermistor) which is the temp sensor line for the board.

The known good reading should be 0.717V
![Samsung S22 Ultra - Charging Connector Temp Sensor Line Diagram.](images/0/0b/S22_Ultra_Connector_Temp_Sensor_Line_Drawing.png)
If you get a low reading like 0.003V, then the line is shorted.
### Repair Steps
To repair the shorted USB_THM line, you must replace the U7002 IC. This is a PMIC inside the Samsung Sandwich.
![Samsung S22 Ultra - U7002 IC that needs to be replaced if USB_THM is shorted](images/a/ab/U7002_diagram.png)
IC name is "Qualcomm PM8350"

This is extremely difficult to do, as the 2 layers are soldered together with lead free high temp solder.

Although, there are a few workarounds to get it to power on & allow you to extract the user data

1. Boot from a DC Power Supply
1. ![Samsung S22 Ultra - Picture of U7002 IC that needs to be replaced if USB_THM is shorted](images/f/f7/U7002.png)Boot with a fully charged battery.
