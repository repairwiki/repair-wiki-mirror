---
title: "IPad 7 Not Charging"
pageid: 7124
revid: 10672
kind: repair_guide
source: "https://repair.wiki/w/IPad_7_Not_Charging"
history: "https://repair.wiki/index.php?title=IPad_7_Not_Charging&action=history"
permalink: "https://repair.wiki/index.php?oldid=10672"
last_edited: "2025-08-25T21:41:16Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPad 7"
  - "Stubs"
infobox:
  Device: "IPad 7"
  Affects_parts: "Motherboard"
  Needs_equipment: "DCPSU, Thermal Camera or freeze spray"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPad 7 Not Charging

## Problem description
The iPad does not charge the battery
## Symptoms
- The iPad does not charge the battery.

### Diagnostic Steps
On iPads that do not charge there is 3 things that are common to fail: the battery, the charge port or the Tristar IC

Start by testing a new battery if possible but if the device does turn on but does not charge the battery may not be the issue.

Inspect the charging port of the iPad for any debris, physical damage, or liquid damage.

If everything is ok the next step is to diagnose the charge circuit.

Start by checking if the 5V from the charger are actually arriving to the main board measure this filter it should have around 5V

![IPad 7 5V input.png](images/c/c7/IPad_7_5V_input.png)
If there is not voltage here with the charger plugged in the replace the charging port flex.

Next check if the voltage is arriving to this mosfet
![Q8550 iPad 7.png](images/7/7a/Q8550_iPad_7.png)
If there is no voltage there or you have less them 5V for example 2V it means that the filters F3700 and F3750 are faulty and must be replaced.

Next check if the mosfet is working the output is the expected 5V if its not Q8550, DZ8550 or R8550 may be faulty.
![Q8550 output.png](images/1/18/Q8550_output.png)

The Tristar U1700 reduces the voltage drop from 600 mV to 30 mV (or less), measure it on the diode scale. If it doesn't drop, swap the Tristar (U1700).
![R1715.png](images/9/9a/R1715.png)
The Tristar used on the iPad 7 is 610A3B, this is common to fail if the user uses bad quality cables.

If you have these symptoms: the iPad charges but only turned off, the iPad only charges in one position.

These issues are related to the Tristar.

## Repair Steps:
The Charge Port is soldered to a flex cable to the mainboard.

To the replace the charge port all you need is flux solder and soldering iron a microscope helps a lot.

Fallow this guide on how to replace it: https://www.youtube.com/watch?v=p10B2fW9zOI

The Tristar  on this model is not underfilled so replacing it not that bad.

To replace the Tristar you will need a hor air station.

- Use your hot air station to desolder the old Tristar from the motherboard.
- Clean the pads on the motherboard thoroughly.
- Reball the new Tristar if it isn't pre-balled.
- Use your hot air station to solder the new Tristar onto the motherboard.

Here is also a video guide on how to replace the Tristar on a iPad 7: https://www.youtube.com/watch?v=YIoUyNI3ajE

## Final Testing
If you replace the charge port make sure the iPad Charges and Data transfer also work, also test that both speakers are working.

If the Tristar was replaced test that the iPad charges and is able to data transfer.
