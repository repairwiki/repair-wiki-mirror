---
title: "Galaxy A125 (Mediatek) Not Booting"
pageid: 4834
revid: 7953
kind: repair_guide
source: "https://repair.wiki/w/Galaxy_A125_(Mediatek)_Not_Booting"
history: "https://repair.wiki/index.php?title=Galaxy_A125_(Mediatek)_Not_Booting&action=history"
permalink: "https://repair.wiki/index.php?oldid=7953"
last_edited: "2025-06-22T22:30:15Z"
contributors:
  - "Ajimalg82"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Galaxy A12"
  - "Stubs"
infobox:
  Device: "Galaxy A12"
  Affects_parts: "Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering, BGA"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Galaxy A125 (Mediatek) Not Booting

## Problem description
The device does not boot and has no response to anything then you could have this issue.
## Symptoms
- Low booting when promted to boot( 0.030 - 0.050 mA)
- Consumes power only when power buttons is pressed and goes to 0.000 as soos as you release it.
- Connect to pc and does nothing
- VPH_PWR voltage is stable
- Buck voltage is not stable

### Diagnostic Steps
- On the wall charger the consumption is under 0.00-0.02 A
- Check for VPH_PWR if its available and stable(3.6-4.2v)
- Check buck voltage with charged battery + charger plugged in (if its not stable then you could have this issue)
- Check VUSB_PMU_CAP diode value to make sure if you have the same exact issue to proceed for repair (should not be 0.000)
![Initial Checking](images/c/cc/Initial_checking.png)

### Repair Steps
This problem occurs due to internal damage in the cpu. This issue is repairable and you should follow the steps below.:

- Remove the PMIC MT6357CRV
- Check the pad #J14 (VUSB_PMU) if its shorted after removing the PMIC (if the pad is not shorted after removing the PMIC then just replace the PMIC.)

![VUSB_PMU](images/3/34/Vusb.png)

- If its still shorted then cover it with some uv mask
- Reball and reinstall the power ic
- Your phone should start working again
