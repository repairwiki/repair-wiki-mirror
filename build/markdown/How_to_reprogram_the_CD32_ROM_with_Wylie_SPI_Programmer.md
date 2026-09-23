---
title: "How to reprogram the CD32 ROM with Wylie SPI Programmer"
pageid: 9311
revid: 13538
kind: other
source: "https://repair.wiki/w/How_to_reprogram_the_CD32_ROM_with_Wylie_SPI_Programmer"
history: "https://repair.wiki/index.php?title=How_to_reprogram_the_CD32_ROM_with_Wylie_SPI_Programmer&action=history"
permalink: "https://repair.wiki/index.php?oldid=13538"
last_edited: "2026-01-01T22:20:41Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPad 10"
  - "Repair guides for IPad Air 4"
  - "Repair guides for IPad Air 5"
  - "Repair guides for IPad Mini 6"
  - "Repair guides for IPad Pro 11in 2nd Gen"
  - "Repair guides for IPad Pro 11in 3rd Gen"
  - "Repair guides for IPad Pro 11in 4th Gen"
  - "Repair guides for IPad Pro 12.9 4th Gen"
  - "Repair guides for IPad Pro 12.9 5th Gen"
  - "Repair guides for IPad Pro 12.9 6th Gen"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How to reprogram the CD32 ROM with Wylie SPI Programmer

## Problem description
Some iPads using the CD3217 USB-C controller IC can develop a no charge, no boot, or low voltage negotiation issue. This typically happens after liquid damage or a power surge. Replacing the CD3217 alone doesn’t fix the issue, because the connected ROM IC is often corrupted or damaged.

This guide is an alternative method to flash the CD3217 ROM. It is **not** a guide on how to repair an iPad with USB-C that does not charge.

See this guide for more info: [How To Program ROM Chip for iPads with CD3217](How_To_Program_ROM_Chip_for_iPads_with_CD3217.md)

## Guide
![200x200px](images/c/c1/Wylie.png)
In this guide we will use a cheaper alternative to the JCID method, this device can be found for around 15€ in websites like Aliexpress.

In order to use this device we must first install the drivers for it, the drivers are available here [https://www.sendspace.com/file/puofuu Drivers]

After downloading the drivers and installing them you need the software to program to Read/Write to the ROM you can find it here [https://www.sendspace.com/file/43kxrq Software]

After downloading the file unpack the RAR and run this program.
![505x505px](images/0/02/Program_to_run.png)To read the ROM, you must first desolder the old ROM from the iPad/iPhone and solder it onto the programmer.

Keep in mind that you must match **Pin 1** correctly. If you solder the IC backwards, you may permanently damage it.

![Pin 1.png](images/f/f9/Pin_1.png)
After having the chip soldered, we are ready to connect the programmer to the computer.

Connect the programmer to the computer, and in the software, click **Detect**. A small window should appear. (If Nothing happens it may be a bad solder connection or a Dead ROM IC)
![Detect.png](images/d/da/Detect.png)

Click on Select ![Chip detected.png](images/6/67/Chip_detected.png)

After selecting the chip, a lot of information about it will be displayed. This is a good sign.
![Chip info.png](images/7/77/Chip_info.png)

Now we can do the actual programming using the dumps in this [https://www.sendspace.com/filegroup/o50KR%2FmFSzssNPV4%2FfMXR%2FabYypKCONhcqYX3llc5ZpMEjLjsYg%2FIrgZTsYR3WPismwz23kyDF0O7ZcGCVfnDg link]

Download the correct ROM for your device from the link above.

After downloading the file, load it into the program.

Click **Open File** and select your file. After the file is loaded, the program will display a message similar to this:
![451x451px](images/e/e4/Rom_Loaded.png)

Then Click on Write
![480x480px](images/6/62/Write.png)

After the program finishes writing, which should only take a few seconds, it will show **100%**.
![426x426px](images/d/d1/Write_ok.png)

After writing is complete, disconnect the programmer from the computer.

Desolder the IC and solder it back onto the motherboard.

After that, the iPad should (hopefully) charge normally again.

And enjoy the fact that you just avoided paying 300€ for something that’s basically the same—just packaged in a fancy device.
