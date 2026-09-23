---
title: "How to Repair iPad Pro 10.5 not charging or not detected by pc"
pageid: 9644
revid: 13944
kind: other
source: "https://repair.wiki/w/How_to_Repair_iPad_Pro_10.5_not_charging_or_not_detected_by_pc"
history: "https://repair.wiki/index.php?title=How_to_Repair_iPad_Pro_10.5_not_charging_or_not_detected_by_pc&action=history"
permalink: "https://repair.wiki/index.php?oldid=13944"
last_edited: "2026-02-12T08:17:46Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPad Pro 10.5"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How to Repair iPad Pro 10.5 not charging or not detected by pc

  - NOTE: USB IC (U3500)  Tristar should match for best compatibility and is compatible with iPhone 7 / 7 Plus (610A3B)**

## Problem description
iPad Pro 10.5” does not charge and is not detected when connected to a computer. The device may show no charging icon, no USB recognition sound on PC, and no data communication.

Replacing the cable and charging brick does not resolve the issue.

In most cases, the fault is related to the U3500 (Tristar) USB controller IC.
![iPad Pro 10.5" Protective Shield covering USB IC (U3500)](images/a/af/Ipad-shield-covering.png)

## Symptoms
- iPad does not charge
- No charging icon
- PC does not detect device
- No USB recognition sound
- New cable and adapter do not fix issue
- Device may still power on if battery has charge

![iPad Pro 10.5" USB IC (U3500) location on board](images/6/65/Ipad-10.5-usb-ic-location.png)
![iPad Pro 10.5" USB IC (U3500) location on board view](images/f/f2/Ipad-10.5-usb-ic-location-boardview.png)

## Solution
### Diagnostic Steps
#### 1. Check Current Consumption
- Connect device to DC power supply
- Press power button
- Verify consumption is below 100 mA at initial click

Low or abnormal consumption supports USB controller fault.
----

#### 2. Perform Dock Test
- Replace charge port with known-good dock flex
- Test charging and PC detection

If charging and detection still fail → dock is not the issue.
----

#### 3. Confirm U3500 Fault
If:

- Consumption behavior is abnormal
- Dock test passes
- No PC detection
- No charging negotiation

Proceed to Tristar replacement.

### Repair Steps
1. Disconnect battery
1. Remove logic board
1. Remove protective armour/shield covering U3500
1. Apply flux
1. Remove faulty U3500 with controlled hot air
1. Clean pads carefully
1. Install known-good U3500
1. Inspect solder joints under microscope
1. Reassemble device
1. Test:

- Charging function
- PC detection
