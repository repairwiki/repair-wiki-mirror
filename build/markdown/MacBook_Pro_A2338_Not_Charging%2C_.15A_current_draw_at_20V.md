---
title: "MacBook Pro A2338 Not Charging, .15A current draw at 20V"
pageid: 9332
revid: 13663
kind: other
source: "https://repair.wiki/w/MacBook_Pro_A2338_Not_Charging,_.15A_current_draw_at_20V"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A2338_Not_Charging,_.15A_current_draw_at_20V&action=history"
permalink: "https://repair.wiki/index.php?oldid=13663"
last_edited: "2026-01-05T06:09:52Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A2338"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A2338 Not Charging, .15A current draw at 20V

## Problem description
MacBook logic board 820-02020 powers on and runs normally from a USB-C power supply and a charged battery but does not charge the battery. The system reports inconsistent power source status, and PPBUS remains at ~12.3V even with the battery disconnected.

Standard USB-C and charging components test normal, and replacing common charging-related ICs does not resolve the issue.
![MacBook Pro A2338 - Detecting Battery Normally](images/e/e2/A2338-detecting-battery.png)
![MacBook Pro A2338 - Current Consumption](images/4/41/A2338-CURRENT-CONSUMPTION.png)

## Symptoms
- Device boots and operates normally
- Runs from USB-C power supply without battery connected
- Battery percentage is visible and health data is readable
- System reports:
  - Power Source: Battery
  - Connected: No
- Battery does not charge
- Same behavior with a known-good battery
- PPBUS_G3H stuck at ~12.3V
- PPBUS voltage does not drop when battery is disconnected
- Device does not drain battery while PSU is connected

## Solution
![[[File:A2338-ud200-location.png|thumb|MacBook Pro A2338 - UD200 IC Location\]\]MacBook Pro A2338 - Normal Battery Health Status](images/0/0f/A2338-normal-battery-health.png)

### Diagnostic Steps
#### 1. Confirm USB-C Input
- Measure:
  - 20V present at USB-C input
- Verify adapter negotiation is normal

✅ If 20V is present, USB-C controllers are functioning
----

#### 2. Verify Battery Detection
- Confirm:
  - Battery data visible (cycles, health, percentage)
- Test with a known-good battery

✅ Battery communication OK
----

#### 3. Measure PPBUS_G3H
- Measure PPBUS with battery connected
- Disconnect battery and re-measure
- Expected behavior: PPBUS_G3H should be between 12.6 V and 13.1 V

❌ Fault confirmed if:

- PPBUS remains ~12.3V with battery disconnected

----

#### 4. Eliminate Common Charging Components
If already replaced with no change:

- CD3217 (both sides)
- USB-C ROM
- Charging IC (ISL)
- Q5265

→ Charging path is not the root cause
----

#### 5. Interpret the Data
If all of the following are true:

- USB-C input is correct
- Battery communication is correct
- PPBUS does not respond to battery removal
- Device runs indefinitely on PSU

Then the fault is PPBUS enable/control logic, not charging hardware.

### Repair Steps
#### 1. Confirm the Fault
1. Connect USB-C power supply
1. Measure PPBUS_G3H
1. * ~12.2–12.4 V present
1. Disconnect the battery
1. Re-measure PPBUS
1. * ❌ PPBUS remains ~12.3 V → fault confirmed

----

#### 2. Eliminate Software Causes
1. Attempt Revive using Apple Configurator
1. Attempt Restore (only if data is not required)

<blockquote>No change confirms hardware-level fault</blockquote>
----

#### 3. Rule Out Common Charging Components
Verify or replace known-good:

- CD32xx USB-C controllers
- USB-C ROM
- Charging IC (ISL)
- Q5265

<blockquote>If PPBUS behavior remains unchanged, continue — charging path is not the issue.</blockquote>
----

#### 4. Identify the Root Cause
- UD200 is responsible for PPBUS control and regulation
- A faulty UD200 can:
  - Hold PPBUS active at ~12.3 V
  - Prevent battery charging
  - Cause incorrect power-source reporting

----

#### 5. Replace UD200
1. Remove logic board
1. Apply controlled heat and remove UD200 IC
1. Clean pads and inspect for damage
1. Install known-good UD200
1. Inspect joints under microscope

----

#### 6. Post-Replacement Verification
1. Reconnect battery
1. Measure PPBUS_G3H
1. * Voltage should now respond to battery connection
1. Connect USB-C adapter
1. Confirm:
1. * Power source switches to Adapter
1. * Battery begins charging
1. * PPBUS rises appropriately during charge
