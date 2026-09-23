---
title: "IPad Pro 9.7 Not Powering on, 2a or Higher Power Draw before Prompt to Boot"
pageid: 5422
revid: 8872
kind: repair_guide
source: "https://repair.wiki/w/IPad_Pro_9.7_Not_Powering_on,_2a_or_Higher_Power_Draw_before_Prompt_to_Boot"
history: "https://repair.wiki/index.php?title=IPad_Pro_9.7_Not_Powering_on,_2a_or_Higher_Power_Draw_before_Prompt_to_Boot&action=history"
permalink: "https://repair.wiki/index.php?oldid=8872"
last_edited: "2025-07-20T19:50:12Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPad Pro 9.7"
  - "Stubs"
infobox:
  Device: "IPad Pro 9.7"
  Affects_parts: "Motherboard"
  Needs_equipment: "Microscope, Thermal Camera, DCPS"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPad Pro 9.7 Not Powering on, 2a or Higher Power Draw before Prompt to Boot

## Problem description
iPad Pro 9.7 not powering on with 2a or higher power draw from DCPS before prompt to boot.
![433x433px](images/f/fb/2+Amps.gif)

## Solution
If this iPad draws any current before prompt to boot it means there is a short on the motherboard.

The first step it to inspect the motherboard for any blown components and water damage.

If there is no water damage, is is most likely a shorted component on any of the below lines:

- **PP_VCC_MAIN**
- **PP_BATT_VCC**
- **PPSTROBE_LX**
- **PPVCC_HIGH**

The most common line to have a short is VCC_MAIN.

To detect the short you'll need to inject voltage (4 V / 2 A) directly into the line you measured as short and use freeze spray (see here https://youtu.be/3MtLSQJvQxI) or thermal camera (see here: https://youtu.be/fkd4iDjgfvc) to spot the capacitor that is shorted.

On this iPad when there is a short on VCC_MAIN U8500 will also get hot dont assume immediately that U8500 is the cause look around the board for other hot spots.
![iPad Pro 9.7 Example](images/b/b7/IPad_Pro_9.7_Example.png)
If the Short is on a Chip you need to replace that component.

If the Short is on decoupling capacitor you can remove it from the board most of the times the capacitance wont drop that much to affect the function of the device.

If there is water damage, corrosion may be the cause of the short sometimes cleaning the corrosion is enough to clear the short however if you see signs of water by a chip it probably means there is water under the IC and you have remove it clean the corrosion aand reball or replace the Chip.

![Water by a chip](images/2/26/Water_by_a_chip.png)

After removing the shorted component you can take a diode reading of the line a healthy VCC Main should have a vault between 0.400 and 0.500.
