---
title: "MacBook Pro A2141 Not turning on, 0.00-0.05a current draw at 5V repair"
pageid: 104
revid: 507
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A2141_Not_turning_on,_0.00-0.05a_current_draw_at_5V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A2141_Not_turning_on,_0.00-0.05a_current_draw_at_5V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=507"
last_edited: "2023-10-29T15:27:22Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A2141"
  - "Stubs"
infobox:
  Device: "MacBook Pro A2141"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A2141 Not turning on, 0.00-0.05a current draw at 5V repair

## Problem description
Facing an issue with the MacBook Pro A2141 (820-01700) displaying 5V and a very low current draw of 0.00 to 0.05A on the USB-C meter.

## Symptoms
- MacBook Pro A2141 stuck on 5V with a current draw of 0.00 to 0.05A on the USB-C meter.
- Not turning on, all voltages missing.

## Solution
![(Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)

### Diagnostic Steps
#### Check for DFU or Recovery Mode
- Connect the MacBook Pro A2141 to another Mac or MacBook via the master port (bottom left side USB-C port).
- Use Apple Configurator 2 to verify whether the device is in DFU or recovery mode.
- If the device is in DFU mode, proceed to "Device stuck in DFU mode due to corrupt firmware" in the repair steps below.

#### Check voltage on PPBUS_G3H
- Normal diode mode reading is ~0.410V
- To accurately measure voltage on PPBUS_G3H, set your multimeter to DC voltage mode and place the black probe to ground and the red probe on PPBUS_G3H. For the 820-01700, the ideal measurement point is F7000.
  - ~12.60–12.65 V = Normal
  - ~12.28–12.35 V = T2 not booted. The likely cause for this is the device is stuck in DFU mode due to corrupt T2 firmware or a failed CD3217. If the board is not in DFU mode proceed to checking below items. Proceed to repair steps below for corrupt T2 firmware if the device is found to be in DFU mode.
  - ~0 V = Short to ground or absent voltage due to a creation problem. Proceed to repair steps below for shorted or absent PPBUS_G3H voltage.

#### Check  voltage on PP3v3_G3H_RTC_X
- Normal diode mode reading is ~0.420V
- To accurately measure voltage on PP3v3_G3H_RTC_X, set your multimeter to DC voltage mode and place the black probe to ground and the red probe on PP3v3_G3H_RTC_X.
  - It is recommended to measure PP3v3_G3H_RTC_X on a capacitor or resistor near one of the CD3217s to rule out a trace/via issue. C3100 is a good place to measure this line on the 820-01700 logic board.
  - ~3.3 V (3.290–3.425 V) = Normal.
  - If PP3v3_G3H_RTC_X = 0V, check for a short to ground by putting your multimeter in continuity or resistance mode, the value should be fairly high, with most boards sitting above 1k Ω. Occasionally you can have a false positive for a short to ground due to capacitance on the line. If this is the case, resistance to ground will be around 60Ω. If this is the case, let the board sit with power disconnected for a few minutes then recheck. *Proceed to PP3v3_G3H_RTC_X low, absent or shorted repair steps below if a problem is found.*

#### Check voltage on PP3v3_G3H_SOCPMU
- Normal diode mode reading is ~0.378V
- To accurately measure voltage on PP3v3_G3H_SOCPMU, set your multimeter to DC voltage mode and place the black probe to ground and the red probe on PP3v3_G3H_SOCPMU.
  - It is recommended to measure PP3v3_G3H_SOCPMU on a capacitor near U7800 to rule out a trace/via issue. C7893/C7869 is a good place to measure this line on the 820-01700 logic board.
  - ~3.3 V (3.290–3.425 V) = Normal.
  - If you measure 0v on this line, you are likely missing PMU_PVDDMAIN_EN which enables U7650 to output this line, this is usually due to R7900 being blown or otherwise damaged.
    - If R7900 blows after replacement, replace U7800 and R7900.
  - Values below the above spec should be considered abnormal. Proceed "PP3v3_G3H_SOCPMU low or absent" in the repair steps below.

### Repair Steps
#### Device stuck in DFU mode due to corrupt firmware
- Revive firmware via Apple Configurator 2.
- Ensure the MacBook is running the latest macOS version for consistent results.
- [https://support.apple.com/guide/apple-configurator-mac/revive-or-restore-an-intel-based-mac-apdebea5be51/mac Follow the provided Apple support article for the procedure.]
- Once plugged in, open Apple Configurator 2. You should see a big square icon pop up that says "DFU" or rarely, "RECOVERY". Click the icon, Navigate to the top menu bar click "Actions" then "Advanced". Select Revive device. You will see a progress bar appear. This process can take over 30 minutes in some cases as Apple Configurator 2 now reinstalls the OS in addition to the M1's firmware. Data will still be retained with the revive option.
- Be cautious that selecting "Restore" will wipe all user data.
- Possible causes for a device to fail a DFU revive include various hardware issues.

#### PPBUS_G3H Short or absent
[How to find short circuits](How_to_find_short_circuits.md)

- If shorted
  - Inject around 1 V with a 5 amp limit into PPBUS_G3H with a DC power supply.
    - A larger tantalum capacitor or the main PPBUS fuse (F7000/F7001) is preferred to inject voltage to, as you will often need a lot of current to be pushed into the line to cause the shorted component to heat up.
    - 1 V is usually sufficient. It is not recommended to inject over 1 V as if one of the CPU VRMs or U9080/U9580 is shorted, you will end up killing the CPU or SSD.
  - With voltage being injected, perform thermal imaging of the board. If thermal imaging is not available, feel around the board to see where it is getting warm. Once the area is localized, add a small amount of isopropyl alcohol to the area to localize the shorted component.
    - Once the shorted component is localized, replace the shorted component.
  - ***If U9080 is the cause of the short, check resistance to ground on L9081, you should have greater than 60 ohms, ideally having more than 1k ohms. If you measure 1-3 ohms, the NAND ICs (SSD) are likely dead.***
  - ***If U9580 is the cause of the short, check resistance to ground on L9581, you should have greater than 60 ohms, ideally having more than 1k ohms. If you measure 1-3 ohms, the NAND ICs (SSD) are likely dead.***
  - ***Normal Diode Mode reading on PP2v5_NAND_SSD0 and PP2v5_NAND_SSD1 is around ~0.400-0.500.***
- If absent without a short:
  - Check that PPDCIN_G3H is making it to the Intersil/Renesas ISL9240 (U7000).
    - Measure PPDCIN_G3H (Normal diode mode reading is ~0.550) with a multimeter in voltage mode at C7024, C7043, C7027, or C7026 on 820-01700.
    - The voltage should match that of the USB-C amp meter (5 V).
    - If 0V is read, check for a short, and if none is found, move to "CD3217 troubleshooting" in the repair steps.
    - If 5 V is read, check the current sensing resistors (listed below) as the ISL9240 may have shorted internally causing the current sensing resistors to blow.
      - Place the multimeter probes on each side of the resistors to measure the resistance, which should be within 5–10% of the reference. If a resistor is found out of spec, replace it and the ISL9240, as the resistor likely blew due to an internal short. Depending on the input voltage, the ISL9240 either buck or boosts the voltage to ~12 V; if USB-C voltage is 5 V, it boosts it
      - R7021, R7022, R7061, R7062 = 1.00 Ω
        - If the current sensing values are normal, replace the ISL9240 (U7000).

#### PP3v3_G3H_RTC_X Short or absent
- The PP3v3_G3H_RTC_X voltage powers the "brain" of the CD3217 USB-C controllers, enabling communication with the USB-C charger to allow for 20 V.
  - If PP3v3_G3H_RTC_X is shorted, low, or absent, the communication between the charger and the device cannot take place, resulting in the device being stuck at 5 V. On the 820-01700, the buck converter U6960 is responsible for lowering the voltage from PPBUS_G3H (approximately 12 V) to 3.3 V to generate PP3v3_G3H_RTC. Therefore, in order to get PP3v3_G3H_RTC, PPBUS_G3H must be obtained first.
- The most common reason for PP3v3_G3H_RTC to be missing or low, is a short to ground, usually on a capacitor around one of the CD3217s, or from a CD3217 itself. If a short to ground is measured, inject voltage at R6935/35 and perform relevant short detection strategies.
- If PP3v3_G3H_RTC_X is not shorted, confirm that the enable signal GHGR_EN_MVR is present, which is generated by the ISL9240 (U7000).
  - The ISL9240 often fails in such a way that prevents GHGR_EN_MVR from being produced. If the enable signal is missing, replacing the ISL9240 (U7000) is recommended. Additionally, due to the capacitance of the circuit, PP3v3_G3H_RTC_X may falsely read as short, measuring around 60-100 ohms. This should be considered a false positive. To confirm, remeasure the PP3v3_G3H_RTC_X after the board has been removed from power for a few minutes.
- PP3v3_G3H_RTC can also be pulled low by PP3v3_UPC_XA LDO, PP3v3_UPC_XB_LDO, PP3v3_UPC_TA_LDO or PP3v3_UPC_TB_LDO, so if you have no measurable short to ground, and your enable/VIN is present, check all the listed rails for a short or low resistance to ground. Low resistance to ground/short on the above LDO lines will usually be caused by a bad CD3217.
  - If a short is found on one of these lines, inspect capacitors on the relevant line for cracks, corrosion or discoloration.
  - If none is found, remove the corresponding CD3217 and remeasure to see if the short is resolved. If the short is measured to be resolved, replace the CD3217. You must source the replacement chip from another 820-01700.
- Occasionally, U6960 may PPBUS_G3H to ground and may blow it's VIN current limiting resistor R6900. Be sure to check voltage on both sides of R6900 if you suspect your VIN may be missing to U6960.

  - If you found and resolved a short circuit, and still have low voltage on PP3v3_G3H_RTC, check voltage on both sides of R6934/35. These resistors can blow in response to a short circuit.**

#### PP3v3_G3H_SOCPMU Short or absent
- If U7650 is not visibly corroded, it is very unlikely that it is the cause of the failure.
  - U7650 must be told to turn on PP3v3_G3H_SOCPMU by the PMU_PVDDMAIN_EN signal which can be measured on R7652. In most cases, it will be missing.
    - If PMU_PVDDMAIN_EN is missing, and PP3v3_G3H_RTC_X is present, measure voltage on BOTH SIDES of R7900.
    - Occasionally due to a trace issue, PP3v3_G3H_RTC will not make it to the resistor, other times, the resistor may be blown. If voltage is low on pin 2, replace the resistor and test the board. If the resistor blows again, replace U7800 and R7900 again, as U7800 is likely pulling too much current and blowing the resistor.
- Other faults causing PP3v3_RTC_G3H_SOCPMU to be missing are rare, but can be related to U7650 and corresponding components. If PMUVDDMAIN_EN is present, check for a short to ground on PP3v3_RTC_G3H_SOCPMU, PP3v3_G3H_T and PP5v_S5_LDO.
