---
title: "IPhone 5 \"FindFlashMediaAndKeepout\" error while booting repair"
pageid: 1632
revid: 3576
kind: repair_guide
source: "https://repair.wiki/w/IPhone_5_%22FindFlashMediaAndKeepout%22_error_while_booting_repair"
history: "https://repair.wiki/index.php?title=IPhone_5_%22FindFlashMediaAndKeepout%22_error_while_booting_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3576"
last_edited: "2024-03-02T12:16:06Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone 5"
  - "Stubs"
infobox:
  Device: "IPhone 5"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Screwdrivers, known good parts, spudger"
  Type: "Soldering, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 5 "FindFlashMediaAndKeepout" error while booting repair

## Problem description
Full error:
 [NAND] _FindFlashMediaAndKeepout:601 physical nand block offset 1
 [NAND] start:356 this  PROVIDER= flashMedia=
 [NAND] WMR_Start:149 Apple PPN NAND Driver, Read/Write
 [NAND] WMR_Start:174 FIL_Init  [OK]
 [NAND] WMR_Open:371 VFL_Open    [OK]
 [NAND] s_cxt_boot:88 sftl: error, unclean shutdown; adopted 6016 spans
 [NAND] WMR_Open:420 FTL_Open    [OK]
 [NAND] _publishServices:642 FTL capabilities: 0x00000001
 [NAND] _ppnvflGetStruct:3469 Checking borrowed blocks - count: 23 max_count: 23
 [NAND] _fetchBorrowedList:881 number of borrowed blocks 16
![An iPhone 5 with water damage displays the `FindFlashMediaAndKeepout` error message.](images/9/90/FindFlashMediaAndKeepout.jpg)

## Symptoms
- Phone displays `FindFlashMediaAndKeepout` error while booting.
- When attempting to restore using iTunes, error 4013 is displayed.

## Solution
- The error is mostly associated with water damage or bad ribbon cables / connections.
- Some users report that unplugging the front camera, the back camera, the camera flash, the proximity sensor ribbon cable or even the whole display assembly can circumvent the issue. This can allow the device to be used or restored with iTunes.
- If the above methods don't work, removing the compass IC (U15) can allow the phone to boot again. The compass IC is located right next to where the front camera ribbon cable plugs in at the very edge of the PCB. It's hidden below some black adhesive tape ([https://www.youtube.com/watch?v=nc1Thaqn3J8 see this video]). The device itself will work fine without the chip, but some functions won't be available (compass, screen auto-rotation, maybe other minor things). If the device boots without the chip, installing a new chip may restore the missing functions.
