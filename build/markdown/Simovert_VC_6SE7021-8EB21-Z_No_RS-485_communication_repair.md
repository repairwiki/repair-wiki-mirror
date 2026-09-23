---
title: "Simovert VC 6SE7021-8EB21-Z No RS-485 communication repair"
pageid: 2072
revid: 4361
kind: repair_guide
source: "https://repair.wiki/w/Simovert_VC_6SE7021-8EB21-Z_No_RS-485_communication_repair"
history: "https://repair.wiki/index.php?title=Simovert_VC_6SE7021-8EB21-Z_No_RS-485_communication_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=4361"
last_edited: "2024-07-17T11:01:46Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Simovert VC 6SE7021-8EB21-Z"
infobox:
  Device: "Simovert VC 6SE7021-8EB21-Z"
  Affects_parts: "ICs SN65HVD1176DR, SN74AHCT08Q"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Simovert VC 6SE7021-8EB21-Z No RS-485 communication repair

## Problem description
Fixing an issue with this Siemens Simovert VC inverter where there is no communication on RS-485.
![ICs to change with marking (Figure 1)](images/4/4c/20240717_125745.jpg)

## Symptoms
- No RS communication otherwise works fine
- ==Solution==

Make sure the port itself is not damaged. If it's okay, check the cable connecting the front panel to the CPU board. If that's also good then replace the 2 ICs marked on figure 1. In this case, replacing both fixed it.
