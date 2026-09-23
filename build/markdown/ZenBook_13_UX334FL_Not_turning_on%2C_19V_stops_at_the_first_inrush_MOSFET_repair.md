---
title: "ZenBook 13 UX334FL Not turning on, 19V stops at the first inrush MOSFET repair"
pageid: 758
revid: 1766
kind: repair_guide
source: "https://repair.wiki/w/ZenBook_13_UX334FL_Not_turning_on,_19V_stops_at_the_first_inrush_MOSFET_repair"
history: "https://repair.wiki/index.php?title=ZenBook_13_UX334FL_Not_turning_on,_19V_stops_at_the_first_inrush_MOSFET_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=1766"
last_edited: "2024-01-08T18:43:26Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for ZenBook 13 UX334FL"
  - "Stubs"
infobox:
  Device: "ZenBook 13 UX334FL"
  Affects_parts: "Motherboard"
  Needs_equipment: "Screwdrivers, multimeter, hot air station, soldering iron"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# ZenBook 13 UX334FL Not turning on, 19V stops at the first inrush MOSFET repair

## Problem description
Repairing a ZenBook 13 UX334FL that does not turn on, and does not charge. This specific issue is related to the inrush limiting MOSFETs.
![Figure 1, input area marked.](images/4/40/Input_area_asus_zenbook.png)

## Symptoms
- Not turning on
- Not charging

## Solution
### Diagnostic Steps
- Measure Vin at the inrush limiter MOSFETS (Figure 1)
- The first MOSFET is not turned on at the gate
  - Responsible is this [https://www.ti.com/lit/ds/symlink/bq24780s.pdf BQ24780s] chip (Figure 2)
  - Here ACDET should be over 2.6V, but is 1.6V
  - So ACOK is not triggered and ACDRV stays 0V
  - The shown short in Figure 3 reduces the voltage![Figure 2, Bq24780s circuit marked.](images/3/3a/Bq24780s.png)

![Figure 4, shorted component.](images/0/09/Short_area_asus_zenbook_13.png)

### Repair Steps
Replace the shorted capacitor.

- This cap pulled VSYS down
- Replaced with 1uF/20V (measured at the other 3 caps, which are the same size).
