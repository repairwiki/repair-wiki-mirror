---
title: "PlayStation 5 Disk to Digital Conversion"
pageid: 3991
revid: 7020
kind: repair_guide
source: "https://repair.wiki/w/PlayStation_5_Disk_to_Digital_Conversion"
history: "https://repair.wiki/index.php?title=PlayStation_5_Disk_to_Digital_Conversion&action=history"
permalink: "https://repair.wiki/index.php?oldid=7020"
last_edited: "2025-05-23T00:08:42Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for PlayStation 5"
  - "Stubs"
infobox:
  Device: "PlayStation 5"
  Affects_parts: "Motherboard, Disk Drive"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# PlayStation 5 Disk to Digital Conversion

## Problem description
Just like the PlayStation 4, the disc drive in a PlayStation 5 is paired to the motherboard. When the PS5 cannot communicate with the Renesas chip, the console is unable to update the system firmware, resulting in errors such as SU-101312-8.
![Error  SU-101312-8[[File:Ps5 bios location.jpg|thumb|PS5 Bios Chip Location\]\]](images/9/9f/SU-101312-8.webp)

## Symptoms
- You purchased a disc version motherboard but are unable to reinstall the firmware.
- The Renesas chip has failed.

## Solution
As of May 18, 2025, there is no way to pair a new disc drive to the console. The only solution is to convert the motherboard to a Digital Version.

    - Note: This guide is only valid for the standard version of the PS5 (FAT).***

### Special Equiment Needed
To convert the console from Disc to Digital, you will need an EEPROM Reader/Writer. The most popular model is the CH341A, which is affordable, reliable, and widely available on websites like AliExpress, eBay, Amazon, etc.

You will also need a SOP8 adapter to connect the BIOS chip to the programmer.

### Repair Steps
To convert the console to a Digital Version, you will need to modify specific values in the PS5 NOR (BIOS).

The BIOS chip (25Q16JVNIM) is located next to the southbridge.

#### Step 1: Remove the BIOS Chip
- Locate the BIOS chip (25Q16JVNIM) next to the southbridge on the PS5 motherboard. Use a hot air station to carefully desolder the chip. Exercise caution and avoid excessive heat, as it can damage the chip.

#### Step 2: Connect and Read the BIOS Chip
- Solder the bios chip to the SOP8 adapter.
- Connect the chip to the programmer.
- Connect your programmer to the computer.
- Read the chip and save a copy of the bios file on your computer it will create a .bin file.

#### Step 3: Modify the BIOS File
#### ***Important: Before opening the BIOS file, create a backup copy.***
To convert the motherboard to a Digital Version, modify two specific offsets in the BIOS file (0x1C7011 and 0x1C7038). Follow these steps.

- Open the BIOS .bin file in a hex editor, such as HxD [https://mh-nexus.de/en/hxd/]
- Press Ctrl + G, enter `001C7011`, and press Enter. This will navigate to the first address. The cursor will highlight a value of **`02`**. Change this value to `03`.
- Press Ctrl + G again, enter `001C7038`, and press Enter. This will navigate to the second address. The cursor will highlight a value of `89`. Change this value to `8D`.
- Save the modified BIOS file.
Your File should look like the image bellow after the modifications
![PS5 Digital Modifications](images/7/76/PS5_Digital_Modifications.jpg)

#### Step 4: Write the Modified BIOS File
Load the modified BIOS file into the programmer software. Write the new BIOS data to the chip using the EEPROM Reader/Writer.

#### Step 5: Reattach the BIOS Chip
Solder the BIOS chip back to the motherboard, ensuring it is in the same orientation as before. Reassemble the console. You may leave the disc drive disconnected if desired.

#### Step 6: Reinstall PS5 Firmware
Reinstall the PS5 system firmware. Follow the official guide on the PlayStation website for detailed instructions: PlayStation Support. [https://www.playstation.com/en-us/support/hardware/ps5/system-software/]

## Final Testing
  - Online Connectivity**: Connect the PS5 to the internet via Wi-Fi or Ethernet. Go to **Settings > Network > Test Internet Connection** to verify a successful connection.

  - PlayStation Store Access**: Open the PlayStation Store, sign in with your PlayStation Network account, and confirm you can browse and download digital games or apps.

  - Game Launch**: Download a small free-to-play game or demo from the PlayStation Store, install it, and verify it launches correctly.
