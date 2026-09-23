---
title: "How To Fix an iPhone 7 That Suddenly Developed a No Service Issue. Baseband Repair"
pageid: 1438
revid: 3142
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_an_iPhone_7_That_Suddenly_Developed_a_No_Service_Issue._Baseband_Repair"
history: "https://repair.wiki/index.php?title=How_To_Fix_an_iPhone_7_That_Suddenly_Developed_a_No_Service_Issue._Baseband_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3142"
last_edited: "2024-01-22T08:36:51Z"
contributors:
  - "VCCBoardRepairs"
anonymous_edits: 0
categories:
  - "Missing device page"
  - "Repair guide"
  - "Repair guides for IPhone 7 Plus"
  - "Repair guides for iphone 7"
  - "Stubs"
infobox:
  Device: "iphone 7, IPhone 7 Plus"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "BGA, Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix an iPhone 7 That Suddenly Developed a No Service Issue. Baseband Repair

## Problem description
iPhone 7 that has Developed the issue with the phone stuck in "Searching" or "No Service" on its own (no previous repair attempts)

Baseband Issue![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- If no previous repairs attempts were made on the phone, but has these symptoms:
  - With no SIM Card installed, the phone is always "Searching..." or "No Service".
    - A working phone will show "No SIM" with no SIM Card installed.
  - Dial *#06# in the phone app, and nothing happens
    - A working phone with no Baseband issue, will make the IMEI pop up.
  - If you go to Settings > General > About > Model Firmware is blank

## Solution
### Intel Model:
- BBPMU_RF (Baseband Power Management Chip) has failed and just needs to be replaced
  - Part# 6826

### Qualcomm Model
- Check for shorts around BBPMU. Probe all large caps around the chip for any shorts.
- If no short, pull BBPMU, run jumpers for the corner ground pads, 98, 93, 88, 83 and attach to ground layer of the board. (Example pic coming soon)
  - To be safe, just replace the chip, vs reballing, as the chip could be bad.
  - ![Bbpmu jumpers.png](images/9/98/Bbpmu_jumpers.png)
- If PP_0V9_LDO3 has a short, replace XCVR1_RF and XVCR0_RF, then check again for a short.
  - If no more short, it should be solved.
- If PP_1V0_SMPS5 gives you a diode mode reading of 0.100 to 0.125 or so, then this line is partially shorted
  - You can "steal" the voltage from PP_1V2_LDO2 at C5627_RF.
  - Set a 1K resistor with 1 leg on C5701_RF, then run a jumper to C5627_RF to connect the rest of the circuit.
  - Refer to this example: https://www.instagram.com/p/Br6AMEbjALH/
- If PP_1V0_SMPS5 has a full short, with a diode mode reading is 0.000, then BBCPU is internally shorted and there's no fix. BBCPU is paired to the CPU and cannot be replaced. If you replace it, it will never get service.
  - Please note:** If you attempt the above repairs, but it's still stuck in "Searching..." or "No Service", then flash an update (**DO NOT RESTORE**). This can sometimes solve the issue. Not sure why it is needed sometimes.

If a phone with a baseband problem is restored, then the iOS software will "erase" the IMEI (baseband info) in the phone and will require the board issue to be fixed, then restored again, so the software will bring back the IMEI.

If you restore, and still has no IMEI, then a baseband/board issue is still present on the board. That will need to be fixed, then restored again.
