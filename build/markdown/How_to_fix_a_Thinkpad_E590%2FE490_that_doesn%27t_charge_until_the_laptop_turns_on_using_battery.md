---
title: "How to fix a Thinkpad E590/E490 that doesn't charge until the laptop turns on using battery"
pageid: 1492
revid: 4175
kind: repair_guide
source: "https://repair.wiki/w/How_to_fix_a_Thinkpad_E590/E490_that_doesn't_charge_until_the_laptop_turns_on_using_battery"
history: "https://repair.wiki/index.php?title=How_to_fix_a_Thinkpad_E590/E490_that_doesn't_charge_until_the_laptop_turns_on_using_battery&action=history"
permalink: "https://repair.wiki/index.php?oldid=4175"
last_edited: "2024-07-01T03:59:01Z"
contributors:
  - "Pandrew"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Thinkpad E490"
  - "Repair guides for Thinkpad E590"
  - "Stubs"
infobox:
  Device: "Thinkpad E590, Thinkpad E490"
  Type: "Soldering, Teardown, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How to fix a Thinkpad E590/E490 that doesn't charge until the laptop turns on using battery

## Problem description
If your laptop charges correctly while it's on, but when reconnecting the charger while the laptop is off it refuses to charge, then this guide might apply to you.

In this case the PD controller chip (U4201: RTS5455) is probably okay, but isn't powered correctly when the laptop is off.
## Symptoms
- After the laptop is turned on (on battery power), it can charge successfully
- Connecting the charger while the laptop is off doesn't charge it
- Checking with a USB-C analyzer shows that only 5V is supplied by the charger

## Solution
### Diagnostic Steps
- With the laptop turned off, and disconnected from the charger, check D4311 with your multimeter's diode mode. If you can't see a <=1.2V diode drop in any of the directions, replace the diode.
  - Make sure to also check downstream devices, for example the capacitor C4306. The diode may have died for a reason.
- Check the output of regulator U4305 should be around 5V, if it's not:
  - Check if the EN pin is high.
    - If the EN pin is low investigate Q4304 and the PD_VBUS_C_CTRL1_EC signal
  - The ADJ pin, should be around 0.6V normally when there is 5V output. Since we're in the situation where there isn't 5V output, we expect there to not be 0.6V on the ADJ pin. If there is, then the regulator is operating correctly, and there's an issue with the feedback resistor divider.
  - Check that the output is not shorted to ground
  - Replace the U4305 regulator.
