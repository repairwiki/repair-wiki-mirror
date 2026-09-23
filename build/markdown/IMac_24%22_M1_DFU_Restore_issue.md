---
title: "IMac 24\" M1 DFU Restore issue"
pageid: 3244
revid: 5981
kind: repair_guide
source: "https://repair.wiki/w/IMac_24%22_M1_DFU_Restore_issue"
history: "https://repair.wiki/index.php?title=IMac_24%22_M1_DFU_Restore_issue&action=history"
permalink: "https://repair.wiki/index.php?oldid=5981"
last_edited: "2025-03-19T04:23:44Z"
contributors:
  - "Stephen"
anonymous_edits: 0
categories:
  - "AIO"
  - "Apple Computer/All In Ones"
  - "Missing device page"
  - "Repair guide"
  - "Repair guides for iMac 24\" M1"
  - "Stubs"
infobox:
  Device: "iMac 24\" M1"
  Affects_parts: "LCD/SCREEN, DAUGHTER IO BOARD, USB C ports"
  Needs_equipment: "Screen Removal Tool, you can purchase these or get them from eBay, or Amazon in a kit."
  Type: "Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IMac 24" M1 DFU Restore issue

## Problem description
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/e/e6/IMac24M1.png)

## Symptoms
- DFU Restore Error when trying to revive or restore an iMac 24" M1
- DFU Restore/Revive Error message kicks off the signal even when using good USB C cables

## Solution
### Diagnostic Steps
Make sure to test the external power supply for iMac 24" M1 Models.  The power supplies are known to fail and sometimes will not allow the iMac to be restored or turn on at all.  A good sourced power supply will suffice.

If you are able to get the iMac into DFU, then the next step is to try to revive (in order to retain DATA if need be) first, then if Revive does not work, Restore method will need to be used (WARNING: if trying to retain DATA, this will completely delete all DATA present on the NAND chips).

If the restore method does not work and you get a DFU restore error such as, "DFU State was forced out of DFU MODE" then more than likely the DFU issue lays into the DAUGHTER IO board inside the computer.  This board is removable and can be ordered online.  These boards are not fully known to fail but some do and this would result in why the iMac 24" M1 device is failing to restore.
### Repair Steps
