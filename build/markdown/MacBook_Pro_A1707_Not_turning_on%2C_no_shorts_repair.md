---
title: "MacBook Pro A1707 Not turning on, no shorts repair"
pageid: 191
revid: 538
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1707_Not_turning_on,_no_shorts_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1707_Not_turning_on,_no_shorts_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=538"
last_edited: "2023-10-29T15:33:16Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1707"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1707"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1707 Not turning on, no shorts repair

## Problem description
#incomplete

Provide a concise description of the issue here. Be  as specific as possible to help readers quickly determine whether or not this is the exact problem they are facing.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Not turning on
- Drawing 0A (no current) on 20V as measured by USB-C meter
## Solution
#### Check for low resistance to ground on SMBUS_SMC_5_G3H_SDA or SMBUS_SMC_5_G3H_SCL
On older MacBooks, this would result in no battery recognition and a lower voltage on PPBUS_G3H—on USB-C models, it actually results in the machine not turning on at all. Can be caused by a tiny speck of conductive material in the battery connector.
#### Check for 0.4 V in diode mode on SMBUS_SMC_5_G3H_SDA and SMBUS_SMC_5_G3H_SCL (red probe on GND)
if it's higher the I²C signals will look funny, not going just between 0 and 3.3 V. Check D6950—it can be blown when the SMC goes.
#### Check voltage on PPBUS_G3H
If you have no or low voltage on this rail, check the repair steps below.
### Repair Steps
#### low resistance to ground on SMBUS_SMC_5_G3H_SDA or SMBUS_SMC_5_G3H_SCL
Clean the conductive material, [https://www.youtube.com/watch?v=PDKlWu1eDFA&t=254s Video]
#### 0.4 V in diode mode on SMBUS_SMC_5_G3H_SDA and SMBUS_SMC_5_G3H_SCL (red probe on GND)
#incomplete
#### Low or no voltage on PPBUS_G3H
It could be bad/dead ISL9239. Also check for ≈2.4 Ω on the two ISL9239 current-sensing circuits. If any of the 1 Ω or current-sensing resistors are blown, replace them first, or you will re-kill any new ISL9239 you try!
