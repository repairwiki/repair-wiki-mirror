---
title: "IPhone 14 Pro Max No Touch"
pageid: 9568
revid: 13831
kind: repair_guide
source: "https://repair.wiki/w/IPhone_14_Pro_Max_No_Touch"
history: "https://repair.wiki/index.php?title=IPhone_14_Pro_Max_No_Touch&action=history"
permalink: "https://repair.wiki/index.php?oldid=13831"
last_edited: "2026-02-03T07:36:59Z"
contributors:
  - "Ajimalg82"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone 14 Pro"
  - "Repair guides for IPhone 14 Pro Max"
  - "Stubs"
infobox:
  Device: "IPhone 14 Pro, IPhone 14 Pro Max"
  Affects_parts: "Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering, Teardown, BGA"
  Difficulty: "4. Specialist"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 14 Pro Max No Touch

## Problem description
iPhone 14 pro/ pro max boots normally but touchscreen does not respond at all. Display shows image, but there is no touch input on the entire panel. Replacing the screen does not fix the issue.

## Symptoms
- Touchscreen not responding at all
- Screen replacement does not fix the problem
- GR on display connector is normal

## Solution
The problem generally is due to a faulty capacitor that is placed on the touch boost line. Replacing the capacitor C9201 fixes the issue.
![Bad Cap](images/8/80/Bad_cap_iphone_14_pro_max.png)
![The bad capacitor](images/c/c5/The_actual_capacitor_iphone_14_pro_max.png)

### Diagnostic Steps
1. Check diode values on the connector, if you see any unusual reading trace it or else continue to the next step if all diode values are good.![Diode value](images/9/98/Diode_value_iphone_14_pro_max.png)
1. Check for voltage on the PP_5V1_TOUCH_VDDTX_S2:
1. * You cannot normally check voltage on this line
1. * In order to check voltage on this line you have to manually enable the ic by giving it an enable signal and here is how to do it:![Schematic](images/9/90/Schematic_Iphone_14_pro_max_touch_boost.png)
1. ** Plug the DCPS cable/ battery to the phone 3.8-4.2 volts
1. ** Inject 1.8v at lowest possible Ampere on pin #31(according to JC DRAWING) to enable the LDO output![Inject Voltage](images/5/56/Inject_voltage_iphone_14_pro_max.png)
1. ** Check the output voltage on pin #44(according to JC DRAWING)![Touch Boost Output](images/3/30/Output_iphone_14_pro_max.png)
1. ** If you get no voltage output then proceed to the repair steps

### Repair Steps
1. Split the board in half
1. Check the capacitor C9201, if shorted it **MUST** be replaced.
  - NOTE:** (if you don't replace this capacitor phone will still have no touch problem)![Bad Cap](images/8/80/Bad_cap_iphone_14_pro_max.png)
1. Recheck for shorts
1. In some rare cases of which short is not cleared:
1. * You have to replace the u9200
1. * Check diode value under the ic before replacing it![Touch ic Diode](images/0/04/Values_under_touch_ic_iphone_14_pro_max.png)
1. * Replace the ic and the capacitor
1. Test the touch function, it should be restored.
