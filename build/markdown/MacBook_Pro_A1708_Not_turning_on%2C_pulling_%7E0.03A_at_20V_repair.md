---
title: "MacBook Pro A1708 Not turning on, pulling ~0.03A at 20V repair"
pageid: 188
revid: 442
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1708_Not_turning_on,_pulling_~0.03A_at_20V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1708_Not_turning_on,_pulling_~0.03A_at_20V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=442"
last_edited: "2023-10-27T10:23:54Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1708"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1708"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1708 Not turning on, pulling ~0.03A at 20V repair

## Problem description
Usually if you have a MacBook which pulls around 35 milliamps at 20V, PPBUS_G3H will be missing as well.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Not turning on
- Pulling ~35 milliamps at 20V as measured by a USB-C meter
- PPBUS_G3H missing

## Solution
Replaced Q7030 and U7000 (ISL9239HI with ISL9239C0) without any changes to the fault. With a partially charged battery, the logic board would offer fan spin and briefly show the battery icon to request the charger to be plugged in. The official power adapter (Type C) would not charge this new battery with 1 charge cycle (vendor supplied). The root cause was with **SMB_SMC_CHGR_SDA.** Voltage on **SMB_SMC_CHGR_SDA** was at 0.8 V while **SMB_SMC_CHGR_SCL** was at 3.3 V when the logic board was powered. Checked the local pull-up resistors being present for this SMBUS shared bus (R5380, R5381). Each was being pulled up to the **PP3V3_G3H** rail (3.42 V). All correct. The faulty component causing this stuck **SMB_SMC_CHGR_SDA** line was at D6950. This TVS diode must have been leaking. Upon removal off the logic board, the resistance to ground for both the SCL and SDA lines increased. Powering up, the **PPBUS_G3H** returned to normal and now the logic board is booting and charging the new battery. In hindsight, do not believe that U7000 nor Q7030 required to be replaced. The SEMTECH **RCLAMP3552T** part at D6950 is available from Arrow and other distributors.
