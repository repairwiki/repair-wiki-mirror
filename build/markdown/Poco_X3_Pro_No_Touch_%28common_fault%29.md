---
title: "Poco X3 Pro No Touch (common fault)"
pageid: 5670
revid: 8955
kind: repair_guide
source: "https://repair.wiki/w/Poco_X3_Pro_No_Touch_(common_fault)"
history: "https://repair.wiki/index.php?title=Poco_X3_Pro_No_Touch_(common_fault)&action=history"
permalink: "https://repair.wiki/index.php?oldid=8955"
last_edited: "2025-07-22T20:35:49Z"
contributors:
  - "Ajimalg82"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Poco X3 Pro"
  - "Stubs"
infobox:
  Device: "Poco X3 Pro"
  Affects_parts: "Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering, Teardown, BGA"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Poco X3 Pro No Touch (common fault)

## Problem description
The touch of the device is not working after a drop or damage by a technician while repairing it.
## Symptoms
- Touch not working

## Solution
Generally in this condition there is the touch protocol line called TOUCH_SPI that gets damaged.

- Check diode value in the marked pins,
  - You should get 0.500-0.700 diode value in these lines.
- Missing resistor:
  - In the condition you got any missing resistor here and if its value is marked with 20Ω then you can run a jumper through
  - if the missing resistor has value 1K Ω (shown in the pic) then you will have to replace it with 1K resistor.

![SPI](images/0/01/SPI.png)

- Here is the origin of these touch lines that come directly from the cpu(color coded to match the image on top):

![Spi from cpu](images/6/6d/Spi_from_cpu_poco_x3_pro.png)
