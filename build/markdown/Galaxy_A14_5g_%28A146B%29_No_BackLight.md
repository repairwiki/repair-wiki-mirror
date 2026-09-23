---
title: "Galaxy A14 5g (A146B) No BackLight"
pageid: 6905
revid: 11250
kind: repair_guide
source: "https://repair.wiki/w/Galaxy_A14_5g_(A146B)_No_BackLight"
history: "https://repair.wiki/index.php?title=Galaxy_A14_5g_(A146B)_No_BackLight&action=history"
permalink: "https://repair.wiki/index.php?oldid=11250"
last_edited: "2025-09-04T06:27:58Z"
contributors:
  - "ASRepairs"
  - "Ajimalg82"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Galaxy A14 5G"
infobox:
  Device: "Galaxy A14 5G"
  Affects_parts: "Motherboard"
  Needs_equipment: "Soldering Iron, Hot-Air Station, Microscope"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Galaxy A14 5g (A146B) No BackLight

## Problem description
Here is the solution and the diagnosing steps for no backlight in the samsung galaxy A146B

## Symptoms
- Phone turns on and charges normally.
- Screen shows only graphics with little to no backlight.
- To properly what is going on in the screen you have to use external source of light
- You have already tried to replace the screen with a new one and the problem is still there.

## Diagnosing
- Physically check the area of the backlight section and check if you see any oil like substance near the coils and other components(replace leaked components)

![light ic components](images/8/8a/Light_ic_components.png)

- Check for shorts in the outputs.

![Inputs and outputs](images/d/da/Inputs_and_outputs.png)

- The fuseable coil(is bypassable) is placed in the LED_ANODE line and if its blown up you will have no GR on the ANODE on the display connector.
  - Bypass it if you have GR on the LED ANODE but not on the ANODE and check
- Check for shorts on diode:
  - The diode should not beep and should not give the same value on both sides of it(LED ANODE and VPH_PWR)
  - If LED_ANODE side shows 0.000 GR then you have to remove the short first
  - Then replace the diode with a new diode(from any backlight section would work)
  - Remove the coils and check for continuity:
    - If any coil has no continuity then you have to replace it.
- Check voltage:
  - VPH_PWR = VDD MAIN 3.7-4.2v
  - LED ANODE = 3.7-4.2v
  - LED KATHODE = 0.00v
- If you have done everything right and you still have no backlight then the problem could be a faulty BackLight IC

### Direct Solution (jumper solution of the most common issue):
Mainly this issue occurs due to damaged LED_ANODE line that sometimes disconnects when high voltage tries to pass through, it shows normal GR but when the phone tries to turn on the screen and give the voltage it turns to OL, to verify this issue you can try to press near the BL ic and see if GR value changes, if so proceed to the following solution:

- Make a jumper from LED_ANODE (on the diode) directly to the LED_ANODE of the display connector.

![Jumper Solution](images/6/68/Jumper_Solution.png)

- Mask it with uv and your phone will be ready to go.
