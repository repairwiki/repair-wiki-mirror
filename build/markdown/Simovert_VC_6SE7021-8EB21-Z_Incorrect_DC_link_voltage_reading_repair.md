---
title: "Simovert VC 6SE7021-8EB21-Z Incorrect DC link voltage reading repair"
pageid: 2073
revid: 4375
kind: repair_guide
source: "https://repair.wiki/w/Simovert_VC_6SE7021-8EB21-Z_Incorrect_DC_link_voltage_reading_repair"
history: "https://repair.wiki/index.php?title=Simovert_VC_6SE7021-8EB21-Z_Incorrect_DC_link_voltage_reading_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=4375"
last_edited: "2024-07-17T11:15:04Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Simovert VC 6SE7021-8EB21-Z"
infobox:
  Device: "Simovert VC 6SE7021-8EB21-Z"
  Affects_parts: "Measure resistor"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Simovert VC 6SE7021-8EB21-Z Incorrect DC link voltage reading repair

## Problem description
Repair of a problem where the rectified DC link voltage reading is incorrect on this Siemens Simovert VC inverter.
![The measure resistors (figure 1)](images/b/ba/20240717_131244.jpg)

## Symptoms
- Incorrect DC voltage reading
- Measuring with MM yields correct voltage but the inverter measures it incorrectly
- Inverter won't run and low DC voltage error

## Solution
On the power board, there is a vertical ceramic resistor that houses 2 resistors inside (figure 1). Desolder it out and measure both resistors, they should measure the same, if not, you'll need to replace the resistor with an external one. Make sure to use a 1% or less tolerance.
