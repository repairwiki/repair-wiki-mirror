---
title: "How To Repair iPhone 13 to 16 pro max Proximity sensor not working"
pageid: 7533
revid: 11180
kind: repair_guide
source: "https://repair.wiki/w/How_To_Repair_iPhone_13_to_16_pro_max_Proximity_sensor_not_working"
history: "https://repair.wiki/index.php?title=How_To_Repair_iPhone_13_to_16_pro_max_Proximity_sensor_not_working&action=history"
permalink: "https://repair.wiki/index.php?oldid=11180"
last_edited: "2025-09-02T05:34:24Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 13"
  - "Repair guides for iPhone 13 Mini"
  - "Repair guides for iPhone 13 Pro"
  - "Repair guides for iPhone 13 Pro Max"
  - "Repair guides for iPhone 14"
  - "Repair guides for iPhone 14 Plus"
  - "Repair guides for iPhone 14 Pro"
  - "Repair guides for iPhone 14 Pro Max"
  - "Repair guides for iPhone 15"
  - "Repair guides for iPhone 15 Plus"
  - "Repair guides for iPhone 15 Pro"
  - "Repair guides for iPhone 15 Pro Max"
  - "Repair guides for iPhone 16"
  - "Repair guides for iPhone 16 Plus"
  - "Repair guides for iPhone 16 Pro"
  - "Repair guides for iPhone 16 Pro Max"
  - "Repair guides for iPhone 16e"
infobox:
  Device: "iPhone 13, iPhone 13 Mini, iPhone 13 Pro, iPhone 13 Pro Max, iPhone 14, iPhone 14 Plus, iPhone 14 Pro, iPhone 14 Pro Max, iPhone 15, iPhone 15 Plus, iPhone 15 Pro, iPhone 15 Pro Max, iPhone 16, iPhone 16 Plus, iPhone 16e, iPhone 16 Pro, iPhone 16 Pro Max"
  Affects_parts: "Proximity Sensor"
  Needs_equipment: "JCID V1SE or V1SPRO, Soldering Iron, JCID Repair Assistant Software"
  Difficulty: "3. Hard"
  Type: "Part Replacement"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Repair iPhone 13 to 16 pro max Proximity sensor not working

## Problem description
Front proximity and ambient light sensor failure after water damage or improper flex replacement. Replacing the flex with a non-programmed or aftermarket part removes auto-brightness and proximity functionality.

## Symptoms
- Auto-brightness toggle missing in Settings.
- Screen does not turn off during calls.
- History of water damage or prior sensor replacement.

## Diagnostic Steps
1. Confirm device history (liquid damage, part replacement).
1. Test proximity function during calls.
1. Check Settings > Accessibility > Display & Text size > auto-brightness toggle.
1. Inspect flex under microscope for corrosion or damage.
1. Confirm issue is not caused by display/logic board.

![JCID Photosensitive Sensor Flex](images/7/72/Photosensitive-sensor.png)

## Repair Steps
#### 1. Prepare Tools & Firmware
- Download the correct IPSW firmware for your iPhone model from [https://ipsw.me ipsw.me] or [https://www.3u.com 3uTools].
- Install JCID Repair Assistant and 3uTools on your computer.
- Have a JCID V1SE/V1S Pro programmer and JCID photosensitive board ready.

----

#### 2. Perform Brushing & Unbind
This step unbinds factory data, preparing the device to pair  a new JCID sensor.

1. Connect the iPhone to your computer and open JCID Repair Assistant.
1. Click Read Phone to detect the device.![Read phone in JCID Repair Assistant](images/8/8c/Read_phone.png)
1. Select Brushing mode.![JCID Brushing Unbind](images/d/df/Jcid_brushing_option.png)
1. Tick both options under Brushing Options to enable unbinding.![Tick these 2 options and select flashing and unbind](images/2/29/Tick.png)
1. Click Start Flashing & Unbinding and select your downloaded IPSW firmware.![Select downloaded ipsw](images/5/5d/Select-ipsw.png)
1. Let JCID complete the brushing/unbind process.![Brushing unbind complete](images/f/f3/Brushing-complete.png)
1. Once done, the iPhone will be in Recovery Mode (expected).
1. Open 3uTools, flash the same firmware using a  Flash.

----

#### 3. Program the New JCID Sensor
1. Connect your JCID V1SE or V1S Pro programmer to your PC.
1. Attach the JCID photosensitive board and the new JCID sensor.
1. In JCID software, click 'Start testing' to verify the new sensor is functional.![Start Testing FPC](images/9/97/Start-testing-fpc.png)
1. Click 'Activate FPC' to pair the new JCID sensor with the iPhone.![Activate FPC](images/2/25/Activate-fpc.png)
1. Once activation is completed, ECID should match in both columns.![ECID Matching](images/0/0e/Matching_ecid.png)

----

#### 4. Install & Test
1. Install the newly programmed sensor back into the iPhone.
1. Reassemble the device carefully.
1. Boot up the iPhone and test proximity sensor and auto-brightness functionality.
