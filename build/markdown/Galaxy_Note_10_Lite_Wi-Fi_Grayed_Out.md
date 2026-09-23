---
title: "Galaxy Note 10 Lite Wi-Fi Grayed Out"
pageid: 9560
revid: 13802
kind: repair_guide
source: "https://repair.wiki/w/Galaxy_Note_10_Lite_Wi-Fi_Grayed_Out"
history: "https://repair.wiki/index.php?title=Galaxy_Note_10_Lite_Wi-Fi_Grayed_Out&action=history"
permalink: "https://repair.wiki/index.php?oldid=13802"
last_edited: "2026-02-01T19:33:36Z"
contributors:
  - "Ajimalg82"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Galaxy Note 10 Lite"
  - "Stubs"
infobox:
  Device: "Galaxy Note 10 Lite"
  Affects_parts: "Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering, Teardown, BGA"
  Difficulty: "4. Specialist"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Galaxy Note 10 Lite Wi-Fi Grayed Out

## Problem description
Wi-Fi is not working or cannot be enabled. The device fails to detect or connect to wireless networks despite no visible board damage.

## Symptoms
- Unable to turn on wifi
![UNABLE TO TURN ON WIFI](images/5/50/Unable_to_turn_on_wifi_note_10_lite.png)
- Stuck on faded blue color(depended on theme of the phone)
![WIFI LIST NOT LOADING](images/c/c2/NOTE_10_LITE_WIFI_LIST_NOT_LOADING.png)
- No wifi list showing in the settings
- Bluetooth doesn't turn on aswell

## Solution
There are three main reasons on this specific device the wifi and the bluetooth stops turning on:
![WIFI IC LOCATION](images/c/c1/WIFI_IC_LOCATION_NOTE_10_LITE.png)

![DIODE VALUE UNDER IC](images/d/d7/Diode_value_under_wifi_galaxy_note_10_lite.png)

1. Cold solder under wfi ic:
  1. Check for any physical damage near the wifi ic
  1. Check for shorts near the wifi ic
  1. Remove the wifi ic
  1. Check diode value under the wifi ic
  1. If all diode readings are normal, reball and resolder the Wi-Fi IC, then test if the issue is resolved.
1. Bad Wifi Ic:
  1. If there is no change after reballing, replace the Wi-Fi IC with a known-good IC from a donor board
  1. If still doesn't work try to retrace the OL pads to see for any open lines
1. Cpu Problem:
  1. If you get any open line from CPU side proceed to reball the CPU
  1. In some cases, all signal lines between the CPU and the Wi-Fi IC may test good, but Wi-Fi functionality will still does not work.
  1. The solution to this is if you tried all the above is to reball a CPU
1. Fixed WiFi:

![WIFI FIXED](images/5/56/Wifi_fixed_galaxy_note_10_lite.png)
