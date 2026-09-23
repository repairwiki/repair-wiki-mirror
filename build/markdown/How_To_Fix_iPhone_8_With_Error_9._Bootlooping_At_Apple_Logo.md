---
title: "How To Fix iPhone 8 With Error 9. Bootlooping At Apple Logo"
pageid: 1502
revid: 3297
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_iPhone_8_With_Error_9._Bootlooping_At_Apple_Logo"
history: "https://repair.wiki/index.php?title=How_To_Fix_iPhone_8_With_Error_9._Bootlooping_At_Apple_Logo&action=history"
permalink: "https://repair.wiki/index.php?oldid=3297"
last_edited: "2024-02-04T13:49:55Z"
contributors:
  - "ASRepairs"
  - "VCCBoardRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone 8"
  - "Repair guides for IPhone 8 Plus"
  - "Stubs"
infobox:
  Device: "IPhone 8, IPhone 8 Plus"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "BGA, Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix iPhone 8 With Error 9. Bootlooping At Apple Logo

## Problem description
How To Fix iPhone 8 that is bootlooping. This is where there is an Apple logo flashing every few seconds & never boots to the home screen.

When you try an update or restore on iTunes, it will give iTunes Error Code 9.

Sometimes, this can happen after a battery replacement.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Flashing Apple Logo
- iTunes Update fails with iTunes Error 9
- iTunes Restore fails with Error 9
- 3u Tools Flash will fail at 19% or 20%

## Solution
If 3uTools Easy Flash gives you a failure at 19% or 20% and 3u Tools iTunes Flash gives you Error 9, then the issue is NAND. You'll need to replace NAND. NAND is the memory/storage chip.

### Compatible NANDs
For iPhone 8 and 8 Plus, you can use the NAND of any of the following devices interchangeably:

- iPhone X
- iPhone XS
- iPhone XS Max
- iPhone 11
- iPhone 11 Pro
- iPhone 11 Pro Max
- iPhone SE 2 (2020)

### NAND Programming Process
  - Requirements**

In order to successfully replace the NAND, you'll need the following from the original device or NAND and write it to the replacement NAND, otherwise it won't activate.

- **SN (Serial Number)**
- **WiFi Mac Address**
- **BT (Bluetooth) Mac Address**

It's also recommended you set these to the correct values, but technically will function fine if you put different values

- **Region** (USA, China, Japan, UK, etc.)
  - LL/A is for USA
- **Color** (Black, White, Rose Gold, Red, etc.)
  - This sets the boot up color of the screen. iPhones with a white screen will boot with a white background and black Apple Logo and vice versa for black screen devices.

### Tools
You can use any NAND programmer that supports iPhone 8/8P

  - JC P13** seems to be the most popular.

  - iRepair P10** is another option, that does NAND programming via the lightning port and uses the available "Purple Mode" exploit.

But is only supported by iPhone 8, 8 Plus and iPhone X.

### What if I don't have the original NAND data?
You can get the required NAND info from above, by reading the original NAND from the device.

In most cases, you should be able to read the NAND data.

If it can't, you'll need to find it elsewhere

- GSX report (You'll need to find someone who offers this service)
- JC P13 Query Code

Sometimes, the GSX report service is not available.

Without the original NAND data, you'll never be able to activate the device unfortunately.

  - Using JC P13 Query Code**

First, you'll need to install the replacement NAND, with any generic data filled in for SN, WiFi, BT, etc..

Then restore the phone & try to activate. It will fail

Then you have to remove the NAND again, put it back into JC P13 and click "Query Code" button on the bottom left. The correct SN, WiFi, BT addresses will appear. Copy paste them & save them somewhere or save a screenshot of it.

Then go back, read the NAND, edit the SN, WiFi, BT addresses and write them again into the NAND

Then reinstall the NAND and restore one more time

Now you should be able to activate the device.
