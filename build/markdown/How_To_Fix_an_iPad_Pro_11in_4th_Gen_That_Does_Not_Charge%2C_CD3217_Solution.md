---
title: "How To Fix an iPad Pro 11in 4th Gen That Does Not Charge, CD3217 Solution"
pageid: 291
revid: 3304
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_an_iPad_Pro_11in_4th_Gen_That_Does_Not_Charge,_CD3217_Solution"
history: "https://repair.wiki/index.php?title=How_To_Fix_an_iPad_Pro_11in_4th_Gen_That_Does_Not_Charge,_CD3217_Solution&action=history"
permalink: "https://repair.wiki/index.php?oldid=3304"
last_edited: "2024-02-04T13:59:31Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPad Pro 11in 4th Gen"
infobox:
  Device: "IPad Pro 11in 4th Gen"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix an iPad Pro 11in 4th Gen That Does Not Charge, CD3217 Solution

## Problem Description
iPad Pro 11in, 4th Generation will not charge. This no charging issue will cause the iPad to appear to have no power unless you are testing using a fully charged battery or power supply.
This issue is normally caused by a faulty CD3217 charging IC. When replacing these components it is important that you use a matching CD3217 chip from a donor motherboard and you will need to swap over the paired ROM chip (U3890- is the ROM chip on this specific model)

This problem can apply to these models:

- A2759
- A2761
- A2435
- A2762

## Symptoms
Typically these symptoms will include the iPad not charging, the device may appear to have no power if your battery is depleted. If your battery still has some charge left you will not see a charging symbol when the charger is plugged in and the battery percentage will not rise.

Using a USB meter you may encounter the following readings 5V 0.620A

With a faulty CD3217, the iPad will remain stuck at 5V, indicating there's a problem. Otherwise, it should be charging at the standard 15V.
![iPad Pro 11in 4th Gen - Not Charging properly. It is only showing 5V charging, instead of 15V](images/8/88/IPad_Pro_11in_4th_Gen_-_Not_Charging.png)

## Solution
### Diagnostic Steps
- First, we must determine that we are dealing with a charging issue and rule out the possibility of a no power issue. (using a charged battery or booting from a power supply)
- Next, we can rule out a faulty charging port by testing with a good known part
- Diode mode around CD3217 checking for any shorted components.

Mainly focusing on the 3 large capacitors next to the chip

- PP_LDO_CORE
- PP3V3_ACE_LDO (Typically the shorted line)
- PP3V3_S2_ACE
![iPad Pro 11in 4th Gen - CD3217 & it's paired ROM location & where to check for shorts.](images/8/87/IPad_Pro_11in_4th_Gen_-_CD3217.png)
If these components are reading short, you know you have a faulty CD2317 charging IC and located your problem.

### Repair Steps
Now that you have identified the faulty component, you will need to remove the faulty CD3217 and check the area for shorts with the chip removed.

If all shorts have been cleared then we will proceed to locating a replacement chip.

These chips can be found on similar iPad Pro model boards with USB C.

Along with the CD3217 chip, you will also need to transfer over the paired ROM chip from the donor motherboard. (without swapping over this second chip your new charging IC will not function)

It is important that you use the ROM chip from the exact board you took the CD3217 from. In this example the ROM chip was U3890 (on most boards this chip will be labeled as 8NXXXX)

For example 8N150, 8N030, etc.
![iPad Pro 11in 4th Gen - Charging properly after CD3217 and ROM Replacement](images/5/55/IPad_Pro_11in_4th_Gen_-_Charging_Properly.png)
