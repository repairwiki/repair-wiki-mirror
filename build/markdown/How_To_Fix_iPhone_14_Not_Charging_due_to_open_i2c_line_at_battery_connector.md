---
title: "How To Fix iPhone 14 Not Charging due to open i2c line at battery connector"
pageid: 9705
revid: 14058
kind: other
source: "https://repair.wiki/w/How_To_Fix_iPhone_14_Not_Charging_due_to_open_i2c_line_at_battery_connector"
history: "https://repair.wiki/index.php?title=How_To_Fix_iPhone_14_Not_Charging_due_to_open_i2c_line_at_battery_connector&action=history"
permalink: "https://repair.wiki/index.php?oldid=14058"
last_edited: "2026-02-22T02:49:33Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 14"
  - "Repair guides for iPhone 14 Plus"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix iPhone 14 Not Charging due to open i2c line at battery connector

## Problem description
iPhone 14 comes in with no charging. The device may power on but does not accept charge from a known-good cable and adapter.

During board-level diagnostics, the line:<blockquote>I2C2_SMC_CHARGER_BI_GG_SDA_1V8</blockquote>at the battery connector measures OL (open line) instead of normal diode/voltage value.

This open data line prevents proper communication between the battery gas gauge and charging subsystem, resulting in no charging.
![iPhone 14/Plus I2C2_SMC_CHARGER_BI_GG_SDA_1V8 Pin Location on Battery Connector](images/0/09/Ip14_I2c2_location.png)

## Symptoms
- Device does not charge
- No charging icon
- Battery percentage may be stuck or inaccurate
- Known-good cable and charger do not fix issue
- No visible damage to charging port
- Device powers on but refuses to increase battery %
![iPhone 14/ Plus Jumper Location on Other Side](images/e/eb/Ip14_i2c2_jumper1.png)
![iPhone 14/ Plus Jumper Location on Battery Connector](images/3/35/Ip14_i2c2_jumper2.png)

## Solution
### Diagnostic Steps
#### 1. Confirm Charging Fault
- Test with known-good cable and brick
- Verify no charging current increase
- Confirm dock flex is not at fault

----

#### 2. Measure Battery Connector I2C Line
- Set multimeter to diode mode
- Probe I2C2_SMC_CHARGER_BI_GG_SDA_1V8 at battery connector

Expected:

- .350 (not OL)

Faulty:

- OL (open line)

----

#### 3. Trace the Line
- Locate corresponding test point or opposite-side pad
- Measure continuity between:
  - Battery connector pin
  - Other side of board / test pad

If no continuity → trace is broken.

### Repair Steps
1. Disconnect battery
1. Locate affected battery connector pin
1. Identify alternative test point / via on opposite side of board
1. Verify donor point has correct diode reading
1. Run a fine jumper wire between:
1. * Working side of the line
1. * Battery connector pin
1. Secure jumper properly
1. Inspect for shorts
1. Reassemble device
