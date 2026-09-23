---
title: "IPhone 15 Pro Max Not Charging and no Touch"
pageid: 4156
revid: 7131
kind: repair_guide
source: "https://repair.wiki/w/IPhone_15_Pro_Max_Not_Charging_and_no_Touch"
history: "https://repair.wiki/index.php?title=IPhone_15_Pro_Max_Not_Charging_and_no_Touch&action=history"
permalink: "https://repair.wiki/index.php?oldid=7131"
last_edited: "2025-05-27T17:42:14Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone 15 Pro Max"
  - "Stubs"
infobox:
  Device: "IPhone 15 Pro Max"
  Affects_parts: "Motherboard"
  Needs_equipment: "Soldering Iron, Hot-Air Station, Microscope"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 15 Pro Max Not Charging and no Touch

## Problem description
The iPhone doesn't charge and touch doesn't work
![iPhone 15 Pro Max Not Charging.(Image by Cell Phone Repair Academy)](images/d/d3/Iphone_15_pro_max_not_charging.jpg)

## Symptoms
- Device doesn't charge.
- Device doesn't charge and touch is also not working.

## Solution
This problem is usually associated with a bad U9500 this chip detects what is connected in the USB C port.

### Diagnostic Steps
The first step is to always rule out faulty parts. Start by testing a new display and battery.

If your device doesn't charge, this doesn't mean the U9500 is bad. This issue can also be caused by a faulty Tigris IC. A good way to test is to try a wireless charger. If the device charges with a wireless charger, it means the Tigris IC is working.

For the U9500 to work, it must have 5V on the pad below. To measure this, you will need to separate the motherboard, connect the charging port, and then connect it to a charger.
![U9500 5V Input](images/b/be/5V_U9500_input.png)
If you measure 5V at the input, it indicates that the U9500 is receiving power and should be functioning.

### Repair Steps
The U9500 doesn't work alone, it functions in conjunction with a ROM IC (U9720). This creates a challenge because we cannot replace just the U9500. To replace the U9500, we must also replace the U9720, and both components need to be sourced from a donor board, specifically from an iPhone 15 Pro Max. **They cannot be sourced from an iPhone 15 or 15 Pro.**

![IPhone 15 Pro Max Charging ICs](images/d/d3/IPhone_15_Pro_Max.png)

#### Replacing the U9500 and U9720
- Use your hot air station to desolder the old U9500 IC from the motherboard, while its still hot desolder the ROM IC U1030.
- Clean the pads on the motherboard thoroughly.
- Reball the new U9500 if it isn't pre-balled.
- Reball the new U9720.
- Use your hot air station to solder the new U9500 IC onto the motherboard.
- Solder the new U9720

After replacing the U9500 and U9720, test if the phone is charging and if the touch functionality is working. To do this, connect the charging port, screen, and battery to the top board. The iPhone 15 Pro Max can power on with just the top board. Plug the phone into a charger and use an amp meter to measure the current the phone is receiving.

After confirming that the phone is charging and the touch functionality is working as expected, the next steps are to reball the bottom board and resolder both boards back together.

## Final Testing
After assembling the phone, ensure every function is working as expected, not just the charging circuit.

Connect the phone to a fast charger and check if it fast charges using an amp meter. If it’s fast charging, it should draw 9V and around 2+ amps, depending on the battery capacity.

Connect the phone to a computer and verify that data transfer is working.

Connect USB-C headphones and confirm that audio is functioning as expected.
