---
title: "Acer Aspire V3-772g Not turning on but led lights are working repair"
pageid: 552
revid: 1247
kind: repair_guide
source: "https://repair.wiki/w/Acer_Aspire_V3-772g_Not_turning_on_but_led_lights_are_working_repair"
history: "https://repair.wiki/index.php?title=Acer_Aspire_V3-772g_Not_turning_on_but_led_lights_are_working_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=1247"
last_edited: "2023-11-25T17:54:01Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Acer Aspire V3-772g"
infobox:
  Device: "Acer Aspire V3-772g"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Acer Aspire V3-772g Not turning on but led lights are working repair

## Problem description
If your lights are blinking, it indicates that power is present, and the 3.3v supply is operational. However, there is a malfunction in another essential component necessary for your computer to initiate properly.
![Picture of a bios battery holder for the acer aspire v3-772g (Figure 1)](images/f/f7/Repair.wiki_for_acer_aspire_v3-772g_picture_of_bios_battery.png)

## Symptoms
- Not tuning on
- LEDs are illuminating

## Solution
Here are few solutions to try:

### Reset the BIOS
Perform a BIOS reset by addressing potential corruption in the system's firmware, responsible for guiding your computer into Windows. This type of corruption, though surprisingly common, can hinder the laptop from understanding the necessary steps to load into Windows.

To reset the BIOS, disconnect both the BIOS battery and the main battery. In the provided image, the gray line marks the location of the BIOS battery. Unplug this battery and wait for at least 1 minute. Subsequently, attempt to power on the laptop. If it fails to turn on, proceed to the other solutions.

### Replace the RAM
- Faulty memory can cause your laptop to behave this way, if possible check the laptop with known working memory.

![Picture of the power button connector on the acer aspire v3-772g (Figure 2)](images/7/71/Acer_Aspire_v3-772g_picture_of_the_power_button_connector.png)

### Check the Power Button
The power button may be broken, use a multimeter to assess pin 3 from the right side, as indicated in blue in figure 2. If you observe 3.3v and notice it dropping to 0 when you press the button, followed by a return to 3.3v when you release the button, it indicates that the power button is functioning correctly.

However, if the power button is not working as expected, short that pin to ground. If the laptop still fails to function after this shorting process, proceed to the next troubleshooting step.
![Winbond 25q32 from acer aspire v3-772g (Figure 3)](images/0/0d/A_picture_of_a_acer_aspire_v3-772g_bios_chip.png)

### Re-flash the BIOS
If your BIOS is severely corrupted and a reset doesn't resolve the issue, you may need to reprogram it. Follow these steps:
![Ch341a with a bios chip (Figure 4)](images/e/e1/Picture_of_ch341a_with_a_bios_chip_inside_of_it.png)
![A picture of Neoprogrammer discovering bios chip (Figure 5)](images/b/b4/Picture_of_Neoprogrammer_discovering_possible_bios.png)

1. Find a BIOS.bin file: Search for a BIOS.bin file for your specific model on the internet. For example, Google "Acer Aspire V3-772G BIOS.bin" to locate and download the required file.
1. Identify the BIOS chip: Locate the BIOS chip on your motherboard; it typically looks like the one shown in figure 3. In this case, it is a Winbond 25q32VS chip. Note that some computers may have two BIOS chips. (Winbond is the company name, 25 probably means the physical size, q32 is how big a capacity it has in magabits.)
1. Acquire a programmer: Obtain a programmer such as EZP2019+ or CH341a, along with the necessary drivers and software. You can find tutorials on YouTube to guide you through the setup process.
1. Prepare for programming: With the programmer ready, use a hot air station to carefully remove the BIOS chip from the motherboard. Figure 4 shows an interface for placing the chip.
1. Software setup: Use software like NeoProgrammer and a CH341a. Follow YouTube tutorials to install the required drivers and software. Use the detect function in NeoProgrammer (Figure 5) to identify your BIOS chip. Ensure all pins make good contact and are in the correct orientation.
1. Identify BIOS type: Once detected, the software will ask for the BIOS type. This information can be found in the manual for the BIOS chip, which is available online. Select the appropriate type; if unsure, find a similar BIOS chip and match the specifications.
1. Backup the BIOS: Before proceeding, read and save a backup of your current BIOS using the read function (green arrowed chip image).
1. Clear and write the BIOS: Next, clear the BIOS chip using the delete function (red X) and then write the new BIOS file using the write function (blue arrow). Note that some BIOS chips cannot be directly overwritten; they need to be cleared first.

By following these steps, you can reprogram the BIOS chip, resolving issues related to severe corruption.
