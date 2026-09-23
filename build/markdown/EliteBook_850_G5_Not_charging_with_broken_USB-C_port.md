---
title: "EliteBook 850 G5 Not charging with broken USB-C port"
pageid: 8729
revid: 14180
kind: repair_guide
source: "https://repair.wiki/w/EliteBook_850_G5_Not_charging_with_broken_USB-C_port"
history: "https://repair.wiki/index.php?title=EliteBook_850_G5_Not_charging_with_broken_USB-C_port&action=history"
permalink: "https://repair.wiki/index.php?oldid=14180"
last_edited: "2026-03-11T18:29:16Z"
contributors:
  - "Cheapskate777"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for EliteBook 850 G5"
  - "Stubs"
infobox:
  Device: "EliteBook 850 G5"
  Affects_parts: "USB C port"
  Needs_equipment: "CH341B, screwdriver, possible solder"
  Type: "Teardown, Software"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# EliteBook 850 G5 Not charging with broken USB-C port

## Problem description
- After disconnecting a USB-C charger, laptop reports power is still plugged in and charging indicator remains solid amber
- Any USB C peripherals are not recognized

## Possible Permanent Fix
This laptop was built around the same time as [Thinkpad T480](Thinkpad_T480.md) and USB-C charging was new. The T480 had issues with the thunderbolt port due to the firmware constantly writing to a 1 MB eeprom chip. Eventually, the chip's storage would overfill and corrupt the firmware.

On the back of the 850's motherboard, there is a winbond 25q80 chip[^1] that is 1 MB. Another user posted the dump of the chip that contained no null padding and seemed like the firmware was written twice and did not have enough room to write a third time.

[https://files.catbox.moe/ho7chu.bin Dump of Elitebook 850 G5 25q80 chip]

[https://files.catbox.moe/3bresl.bin Dump of original T480 eeprom (notice size is smaller than 1MB and does not have padding)]

[https://files.catbox.moe/cz7za8.bin Dump of correctly padded T480 eeprom]

Checking the official driver page and extracting the thunderbolt firmware for this Elitebook, the .bin file is 245 kB which is similar size to the original T480 firmware.

In theory it might be possible to create a padded version of the Elitebook's thunderbolt firmware and follow [https://github.com/SkippyHub/Lenovo-thinkpad-T490-thunderbolt-eeprom-fix these steps].

I have not tried flashing the chip, do at your own risk!

## Temporary Solutions
I bought a USB C to barrel jack connector very cheap on AliExpress which bypasses the faulty USB-C for charging.

Otherwise, doing a hard reset (press the power button for 10 seconds and the caps lock and num lock will flash) returns USB C functionality.

## Possible (random luck) Fixes
![Elitebook 850 G5 BIOS Chip](images/f/fc/Elitebook_850_G5_Bios_Chip.jpg)
I downgraded the BIOS to 1.08 which is the version before Intel patched plundervolt. I noticed the failure rate dropped from 100% to around 50% after changing the BIOS. To downgrade you must use a CH341b flasher. The standard clamp does not fit on the chip's package and you must use some solder to connect the pins.

1.08 BIOS version https://ftp.hp.com/pub/softpaq/sp98501-99000/sp98706.exe (Cannot flash with software, you must splice the binaries of your current chip dump and the new BIOS)

- To downgrade, first get the dump of your current BIOS chip using the CH341b tool
- Extract the .bin file from the .exe
- Follow https://www.youtube.com/watch?v=6vt48k2zF4A [https://preservetube.com/watch?v=6vt48k2zF4A Archive](https%3A%2F%2Fpreservetube.com%2Fwatch%3Fv%3D6vt48k2zF4A_Archive.md) to add the downgraded BIOS hex to your current chip's dump
- Flash the edited binaries to your BIOS chip using the CH341b tool

![Possible way to connect CH341b flasher to BIOS chip without desoldering the chip from the board. Useful if you do not have access to heat gun and flux. The 'wires' are pieces of solder.](images/d/d2/Elitebook_850_G5_BIOS_Chip_Flashing.jpg)
One day the USB C port stopped failing at all without any BIOS/hardware updates. However, I regularly update Linux and currently using 6.12.57+deb13-amd64 without any USB issues. I noticed that turning off UCSI mode in the BIOS power settings also enables the USB C charging.

[^1]: https://www.badcaps.net/forum/troubleshooting-hardware-devices-and-electronics-theory/troubleshooting-laptops-tablets-and-mobile-devices/bios-requests-only/79339-hp-elitebook-850-g5-bios-password
