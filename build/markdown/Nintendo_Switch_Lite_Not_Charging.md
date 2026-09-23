---
title: "Nintendo Switch Lite Not Charging"
pageid: 5906
revid: 9235
kind: repair_guide
source: "https://repair.wiki/w/Nintendo_Switch_Lite_Not_Charging"
history: "https://repair.wiki/index.php?title=Nintendo_Switch_Lite_Not_Charging&action=history"
permalink: "https://repair.wiki/index.php?oldid=9235"
last_edited: "2025-07-28T22:02:45Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Nintendo Switch Lite"
  - "Stubs"
infobox:
  Device: "Nintendo Switch Lite"
  Affects_parts: "Motherboard"
  Needs_equipment: "Microscope, Soldering iron, multimeter"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Nintendo Switch Lite Not Charging

## Problem description
The device does not charge
![Components related to charging](images/3/38/Switch_Lite_charging_circuit.jpg)

## Symptoms
- The device doesnt charge

## Solution
Before assuming you have a board problem you should try a new a battery and another charger.

### Diagnostic Steps
The first step is to inspect the charging port for any physical damage like: Bent pins, liquid damage, or dust.

If every thing is ok the next thing to do is with a Mechanic T-824 take diode readings of the USB port.
![300x300px](images/5/5c/Nintendo_Switch_Lite_-_Mechanic_Readings.png)
Note: It is normal for pins 08 and 17 to be OL since this device doesnt have Video output the P13 IC is not present.

The next thing i like to check is if the fuse is ok, to do this put your multimeter in continuity mode and listen for the beep if it beeps the fuse is OK.

With and amp meter between the charger and the console measure the voltage, with a original charger it should be at 15V, if its not this means the M92T36 IC is not talking to the charger.

If you only have 5V on the charger it means the M92T36 is not working, check the capacitor around the M92T36.

If you find no shorts it is recomend to replace the M92T36 IC.

If even after doing all the above check the device does not charge the final option is to replace the BQ24193 this chip is the actual component that charges the battery.

## Repair Steps
### Replace the USB-C port
The easiest way to replace the USB-C port is to use the "hot swap" method it consists of heating the port from below and when the solder is liquid you lift the old port and install the new one while the solder is still liquid, there are a few videos on youtube how to this heres an example.

After soldering the new port make sure every pin as a good connection to the pad on the motherboard.

Make sure the solder flooded well on the anchor points both on the top side of the board and the bottom.

### Replacing the M92T36
Desoldering the Old Chip:

- Apply heat to the M92T36 chip from above using a hot air station or soldering iron. Heat for several seconds until the factory solder begins to melt.
- Gently nudge the chip with tweezers. If it moves, it’s ready to be lifted off.
- While the board is still hot, use solder wick and a soldering iron to clean old solder from the motherboard pads.

Preparing the Motherboard and New Chip:

- Apply a thin layer of new solder to the cleaned motherboard pads. Avoid excess solder, especially in the center square.
- Pre-tin the pads of the new M92T36 chip with a small amount of solder to ensure good contact.

Soldering the New Chip:

- Align the new chip on the motherboard. Match the dot on the chip to the small triangle marker on the motherboard for correct orientation.
- Heat the chip from above using a hot air station. Watch for the solder to melt, indicated by slight chip movement.
- Gently touch the chip with tweezers to let surface tension settle it into place. Avoid excessive force.

Inspection and Cleanup:

- Inspect all connections under a microscope . Ensure there are no solder bridges between pins.
- If any connections look faulty, gently touch the affected pad with a soldering iron to reflow and correct.

  - Note: There are a lot of sellers selling fake/faulty M92T36 chips, it is recomend to buy from a seller with good reputation**

## To Replace the BQ24193
Follow the same steps for the M92T36

## Final Testing
Connect the console to a charger and check if the console negotiates 15V with the charger also check if the console is drawing any current(AMPS).

Make sure you are able to charge the console from both sides of the cable.
