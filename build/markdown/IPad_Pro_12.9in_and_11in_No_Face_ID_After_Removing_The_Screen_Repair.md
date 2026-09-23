---
title: "IPad Pro 12.9in and 11in No Face ID After Removing The Screen Repair"
pageid: 276
revid: 731
kind: repair_guide
source: "https://repair.wiki/w/IPad_Pro_12.9in_and_11in_No_Face_ID_After_Removing_The_Screen_Repair"
history: "https://repair.wiki/index.php?title=IPad_Pro_12.9in_and_11in_No_Face_ID_After_Removing_The_Screen_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=731"
last_edited: "2023-11-05T22:18:56Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Missing device page"
  - "Repair guide"
  - "Repair guides for IPad Pro 12.9 5th Gen"
  - "Repair guides for iPad Pro 11in 1st Gen"
  - "Repair guides for iPad Pro 11in 2nd Gen"
  - "Repair guides for iPad Pro 11in 3rd Gen"
  - "Repair guides for iPad Pro 11in 4th Gen"
  - "Repair guides for iPad Pro 12.9 3rd Gen"
  - "Repair guides for iPad Pro 12.9 4th Gen"
infobox:
  Device: "iPad Pro 12.9 3rd Gen, iPad Pro 12.9 4th Gen, IPad Pro 12.9 5th Gen, iPad Pro 11in 1st Gen, iPad Pro 11in 2nd Gen, iPad Pro 11in 3rd Gen, iPad Pro 11in 4th Gen"
  Affects_parts: "Face ID"
  Needs_equipment: "Screwdrivers, known good parts, spudger"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPad Pro 12.9in and 11in No Face ID After Removing The Screen Repair

## Problem description
The newer iPad Pro's with Face ID are prone to getting Face ID Is Not Available after opening up the device. So what you'll see is, when trying to setup Face ID, you'll get an immediate pop up error like in the example pic below.

This applies to these models:

- iPad Pro 12.9 3rd Gen (2018)
- iPad Pro 12.9 4th Gen (2020)
- iPad Pro 12.9 5th Gen (2021)
- iPad Pro 11in 1st Gen (2018)
- iPad Pro 11in 2nd Gen (2020)
- iPad Pro 11in 3rd Gen (2021)
- iPad Pro 11in 4th Gen (2022)
![iPad Pro with No Face ID. Face ID is not available](images/e/e6/IPad_Pro_No_Face_ID.png)

## Symptoms
- Face ID Is Not Available. Try setting up Face ID later
- No Face ID
- Can't setup Face ID
- Unable to activate Face ID on this iPad
![Unable To Activate Face ID error message](images/8/86/Unable_To_Activate_Face_ID.png)

## Solution
### Diagnostic Steps
![iPad Pro Top Flex Diagram - Names all the sensors on the top flex & their names.](images/e/e4/IPad_Pro_Top_Flex_Diagram.png)
If Face ID was working before you opened the iPad, then In most cases, this is caused by a damaged Ambient Light Sensor (ALS).

They are really easy to damage during the opening of an iPad screen. But before you assume it's the the ALS sensors, be aware that you cannot just replace this whole flex.

The Flood Illuminator at the center of the flex, is part of the Face ID system. If you don't have the original, you lose Face ID, therefore, it cannot be replaced.

Also, you must have the original Dot Projector (TrueDepth Camera) and IR Cam. Without any of these original parts, you will never get Face ID working again.

The ALS sensors themselves, are not part of the Face ID system & can be replaced.

So what you need to do is, look at the ALS sensors from the top side & check for any damage. For example:
![Damaged ALS Sensor on iPad Pro. You can see the sensor is partially lifted from the flex cable.](images/e/e4/IPad_Pro_Top_Flex_Diagram.png)

### Repair Steps
To solve this, you have 2 options

1. Workaround (Easy fix) - Cut the sensor completely off the flex. You can cut it with scissors and just leave off the sensor completely.![iPad Pro with No Face ID - Example of where to cut off the damaged ALS sensor to fix Face ID.](images/5/5c/Damaged_ALS_Sensor_on_iPad_Pro.png)
1. Proper Fix (Difficult) - This requires soldering. You would need to desolder the ALS portion of the flex. This is the long portion of the flex that goes from one ALS sensor to the other.![The iPad Pro top flex is made of 2 flex cables soldered together.](images/7/77/Example_Cut_for_Face_ID.png)You can find the solder joints under a sticker in the middle of the flex.![iPad Pro Face ID Flex - Location of sticker over solder joints](images/8/86/IPad_Pro_Top_Flex_Diagram_2.png)Using a soldering iron and/or hot air, desolder the old flex that has the damaged ALS sensors. Then you can test the flex without any ALS sensors to confirm if Face ID is fixed. If so, then proceed to install a new ALS flex cable. You would need to pull it from a new flex.![Here is where the Top Flex Solder Joints for an iPad Pro are located.](images/a/a4/ALS_Sticker.png)Once the ALS issues are fixed, you should get Face ID working![iPad Pro now has Face ID working](images/a/aa/Top_Flex_Solder_Joints.png)

In either case, Auto Brightness and True Tone should still work too.
