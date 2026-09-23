---
title: "Thinkpad T490 Bios Password Removal"
pageid: 1110
revid: 2622
kind: repair_guide
source: "https://repair.wiki/w/Thinkpad_T490_Bios_Password_Removal"
history: "https://repair.wiki/index.php?title=Thinkpad_T490_Bios_Password_Removal&action=history"
permalink: "https://repair.wiki/index.php?oldid=2622"
last_edited: "2024-01-15T16:58:30Z"
contributors:
  - "Admin"
  - "Pandrew"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Thinkpad T490"
infobox:
  Device: "Thinkpad T490"
  Affects_parts: "MEC1633"
  Needs_equipment: "Soldering Iron; Glasgow Interface Explorer (or other EC programmer), Screwdrivers, Spudgers"
  Type: "Soldering, Software"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Thinkpad T490 Bios Password Removal

## Problem description
This guide describes how to remove a Power-On / Supervisor / System Management Password that the laptop might ask for during boot, or while entering setup.

This guide does **not** apply to hard-drive passwords.
![Power-On/Supervisor/System Management Password promt. (Figure 1)](images/a/a1/Lenovo_Power-On,_Supervisor,_or_System_Management_password_prompt.jpg)
![Hard-Drive Password promt -- This guide does not apply! (Figure 2)](images/f/ff/Lenovo_Hard=Drive_Password_Prompt.jpg)
![The area we will be working on (Figure 3)](images/e/ed/T490_JTAG_pads_area.JPG)
![Move this resistor to a new location (Figure 4)](images/0/06/Thinkpad_t490_move_the_trst_pull_resistor.jpg)
![JTAG Pinout (Figure 5)](images/7/70/Thinkpad_t490_jtag_pinout.jpg)
## Symptoms
- The screen shows the BIOS password icon (Figure 1)
- The screen must **not** show the HDD password icon (Figure 2)

## Solution
### What you need
- Screwdrivers to open up the laptop, and take out the motherboard
- Spudgers to get the bottom case clips to release
- Hot air, two soldering irons, or soldering tweezers, and the skills to safely move an 0201 size resistor
- Some wires to be soldered to the unpopulated JTAG footprint on the bottom of the board
- A tool that can program the MEC1663 EC chip, for example the open hardware [https://glasgow-embedded.org/latest/intro.html Glasgow Interface Explorer], but proprietary alternatives also exist
- Potentiall you may also need ThinkPad Serial Number Update Utility on a bootable usb drive

### Repair Steps
- Attempt to enter the bios with an empty password, and if successful, you may get partial access to the BIOS settings, take a screenshot of the main screen showing various serial numbers.
- Take off the bottom cover
- Disconnect and remove the main battery
- Disconnect the CMOS battery
- You have to fully take out the motherboard, because the necessary pads are on the other side:
  - Disconnect the trackpad ribbon cable on the trackpad side
  - Remove the trackpad screws
  - Remove the mouse button keycaps
  - Underneath the mouse button keycaps unscrew the screws holding the keyboard assembly in place
  - Slide the keyboard assembly towards the screen, and tilt it up
  - Gently disconnect the keyboard assembly flex cables from the motherboard
  - Disconnect any remaining connectors from the motherboard
  - Remove the IO bracket screws, and any other screws holding the motherboard in
    - Keep the cooling system screws in. They do not interfere with taking out the motherboard, and we will need to reprogram the EC while the laptop is powered, so it's safer to leave the cooling system on the board. (Also keep the cooling system plugged in)
    - Beware that the thin heat-pipe is very fragile, and it can barely hold the weight of the fan. Do not apply any unnecessary force to it, or it will be crushed.
  - Take out the motherboard. We will be working with the area shown in Figure 3.
- Move the TRST resistor from pull-down to pull-up position. See Figure 4 for exact placement.
- Solder wires to the JTAG pins. See Figure 5 for the pinout. Note that with Glasgow Interface Explorer you don't need to worry about the exact pinout of the signals, because the tool can auto-detect it for you, just make sure you get the GND pin right, and that you solder a wire to all other pins except for pin 6.
- Connect the motherboard to a charger
- Use your EC programmer tool to manipulate the EEPROM, to remove the password. You have two options:
  - Read an EEPROM image and try to guess at what offsets the passwords are stored, and try clearing only those areas. The exact offsets might differ from one EC firmware version to another.
    - See the section "EEPROM Offsets" for more information
  - Completely erase the EEPROM content
    - In this case you will have to restore the system and board serial numbers, otherwise you will keep getting error messages during boot
    - This way UUID cannot be restored
- Disconnect the charger
- Restore the TRST resistor to its pull-down configuration, and remove the jtag wires (You may be able to test if password removal was successful without repeatedly moving the resistor back and forth, Temporarly leaving the resistor in the pull-up state has worked for the author, but it may not always work. It is definitely recommended to restore the resistor at the very end.)
- When reassembling the laptop make sure that reconnecting the battery is the last step taken.
- If you have erased the EEPROM completely, then you will have to restore the laptop serial numbers. In this case use ThinkPad Serial Number Update Utility.
  - Initialize the EEPROM
  - Assign UUID
  - Set system identification
    - Add "C0" S/N data. The long form serial number should be concatenated from: "1S", the "Type" on the bottom sticker, and the Serial Number on the bottom sticker, without dash symbols or date codes
      - Example: the bottom sticker says "TYPE 20N3-012345   S/N PF-678901", then the input code should be "1S20N3012345PF678901"
    - Add "B0" S/N data. The long form board serial number should be printed on a sticker on the motherboard, right under the RAM slot cover, it's written in small font. The long form board serial number should look like this: "8SSBxxxxxxxxL1HFxxxxxxx". The second half of it should match the board serial number as may have been seen previously in the bios.

### EEPROM Offsets
- With EC firmware version N2IHT39W (1.23)
  - For the supervisor password, try setting to 0xFF offsets: 0x302, 0x303, 0x310..0x34f
  - For the system management password, try setting to 0xff offsets: 0x380..0x39F

### Programming the MEC1663 EEPROM
#### General knowledge about the MEC1663
This chip contains the following memories:
- 256KiB of embedded flash, which usually contains EC firmware
- 2KiB of EEPROM, which usually contains the BIOS password(s), and serial numbers

There are 3 ways to clear BIOS password(s) from the EEPROM:
- Erase all of the eeprom, using normal eeprom access commands
- Read the eeprom, modify the image with a hex editor, and write it back
- Emergency erase command: this will erase both the embedded flash memory, and the eeprom
  - The advantage of the emergency erase is that it will work even if protection features are enabled in the MEC (so far no protection features have been observed to be enabled)
  - An emergency erase can always be performed, even if it's not strictly needed. However protection features are enabled, and emergency erase is the only way to erase the eeprom, then it is not possible to read out the entire EC firmware, so in order to not brick the laptop, you will need to get a complete EC firmware image to program into it, and you cannot get it by reading it from the MEC.
  - For these reasons we don't recommend using the emergency erase method: it is more risky and provides no advantages (for now).

The embedded flash can also be erased using normal flash access commands, however that will not result in the removal of the BIOS passwords(s).

Therefore we recommend using methods that touch the EEPROM memory only. (if the manufacturer will start enabling protection features in a future version of the firmware, then we will update this recommendation)

#### Using the Glasgow Interface Explorer
##### 1. Connect the Glasgow to the JTAG interface
Connect the TDI/TDO/TMS/TCK pins in any order to any pins marked with numbers on Port A or Port B

Connect the GND pin to one of the "G" pins of the Glasgow

##### 2. Determine the JTAG pinout
Glasgow will do this automatically for you, just run:

`$ glasgow run jtag-pinout -V 3.3 --pins-jtag 0:15`

This command will print something like this on its last line:

`I: g.applet.interface.jtag_pinout: use `jtag-probe -V 3.3 **--pin-tck 12 --pin-tms 15 --pin-tdi 14 --pin-tdo 13**` as arguments`

The following commands show example values for the --pin-* arguments. Instead of those examples copy-paste the values the first command returns for you.

##### 3a. Read/Modify/Write the EEPROM
`$ glasgow run program-mec16xx -V 3.3 **--pin-tck 12 --pin-tms 15 --pin-tdi 14 --pin-tdo 13** -f 4000 read-eeprom dump.bin`

Edit dump.bin with hex editor

`$ glasgow run program-mec16xx -V 3.3 **--pin-tck 12 --pin-tms 15 --pin-tdi 14 --pin-tdo 13** -f 4000 write-eeprom dump.bin`

##### 3b. Erase the EEPROM
This is useful if you cannot figure out the offsets where the password is stored or if you don't want to bother with multiple cycles of making a change, writing it to eeprom, and power cycling the laptop in a half-assembled state, to see if the password removal was successful.

`$ glasgow run program-mec16xx -V 3.3 **--pin-tck 12 --pin-tms 15 --pin-tdi 14 --pin-tdo 13** -f 4000 erase-eeprom dump.bin`

#### Using other EC programming tools
Make sure whatever tool you use, it falls into one of the two categories below:
1. It supports reading/writing the EEPROM, without erasing the flash
1. We don't generally recommend using emergency erase, but if your tool doesn't support EEPROM access, you may still be able to use it, saving the 256KiB firmware, performing an emergency erase, and writing back the firmware. But some caveats apply:
1. * Make sure that the tool is able to read (and write) the full 256KiB flash. If your tool only reads 192KiB, then you are losing data, and you might brick your laptop
1. * Make sure that the type of erase performed by your tool is of the emergency erase type. If your tool only performs a simple flash erase, then the bios password will stay in place.
Not tested by the authors of this page, but the following information was found online, please take the following with a grain of salt, we cannot confirm any of this:

- Vertyanov JIG ver. 8.1.7897.157 supports reading and writing the eeprom. Select a MEC16xx variant from the drop-down that has EEPROM. Demo video shows the user selecting MEC1653, then select EEPROM only from the second dropdown.[^1]
- RT809F with software version 20220830 may be able to read/write the full 256KiB of flash memory, when selecting MEC1633_256K in the "Partnumber" list. No evidence seen on this video for support of EEPROM-only mode, so if it works, it will only be able to do the emergency erase method.[^2]
- There is some evidence that SVOD3 can read/write 256KiB of flash, based on forum comments.[^3][^4]
  - However there's also some evidence against it. Here's a post saying SVOD3 with Software version 1.1.1.6 date 13.06.2021 only saves 192KiB[^5]
- SVOD4 programmer Software Version 0.0.2.9 date 7.02.2023 Appears to have support for EEPROM-only mode, based on screenshot posted to the Svod-Project facebook group. Select "eeprom" under the "Config MEC" button.[^6]

## References

[^1]: https://www.badcaps.net/forum/troubleshooting-hardware-devices-and-electronics-theory/troubleshooting-laptops-tablets-and-mobile-devices/bios-requests-only/74632-mec-16xx-dump-with-info-block/page4#post1563253
[^2]: See screenshot at timestamp 21:18 https://youtu.be/PyJhlwxCI5w?si=zlg9wAAuN7zEzdmW&t=1278
[^3]: https://www.badcaps.net/forum/troubleshooting-hardware-devices-and-electronics-theory/troubleshooting-laptops-tablets-and-mobile-devices/bios-requests-only/74632-mec-16xx-dump-with-info-block?p=1532683#post1532683
[^4]: https://www.badcaps.net/forum/troubleshooting-hardware-devices-and-electronics-theory/troubleshooting-laptops-tablets-and-mobile-devices/bios-requests-only/74632-mec-16xx-dump-with-info-block?p=1685719#post1685719
[^5]: https://www.badcaps.net/forum/troubleshooting-hardware-devices-and-electronics-theory/troubleshooting-laptops-tablets-and-mobile-devices/bios-requests-only/74632-mec-16xx-dump-with-info-block?p=1547780#post1547780
[^6]: https://www.facebook.com/photo?fbid=566747665500228&set=pcb.566747722166889
