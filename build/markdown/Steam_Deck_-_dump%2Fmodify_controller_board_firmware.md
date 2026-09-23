---
title: "Steam Deck - dump/modify controller board firmware"
pageid: 2519
revid: 5113
kind: other
source: "https://repair.wiki/w/Steam_Deck_-_dump/modify_controller_board_firmware"
history: "https://repair.wiki/index.php?title=Steam_Deck_-_dump/modify_controller_board_firmware&action=history"
permalink: "https://repair.wiki/index.php?oldid=5113"
last_edited: "2024-10-24T09:16:37Z"
contributors:
  - "DawidMurawski"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Steam Deck"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Steam Deck - dump/modify controller board firmware

## WARNING! Only modify the firmware of the controller board, if you know what you are doing or are willig to sacrifice the controller board/Steam Deck. Modifications to the firmware can cause damage to the Software/Hardware of the controller board/Steam Deck.
## Necessary Software:
All tools can be found in SteamOS under

- /usr/share/jupiter_controller_fw_updater*

They can also be found in the online repository:

- https://gitlab.com/evlaV/jupiter-hw-support/-/tree/master/usr/share/jupiter_controller_fw_updater/*

### RFP-CLI
To dump the controller board firmware, the Renesas Flash Programmer CLI is used in this guide.

It can be used to read/write to the MCU via USB.

It can be found under

- /usr/share/jupiter_controller_fw_updater/RA_bootloader_updater/linux_host_tools/rfp-linux-x64*

The documentation for the rfp-cli program contains is a list with useful commands. Unfortunately, you have to download and install the Renesas flash programmer to read it.

- https://www.renesas.com/en/software-tool/renesas-flash-programmer-programming-gui#downloads*

The documentation "rfp-cli.md" can be found in the "docs" folder in the install directory.

#### Examples of Processing from Command Lines with the Use of rfp-cli
Examples are listed in the guide below (starting with page 14)

https://www.renesas.com/en/document/apn/renesas-flash-programmer-usage-command-line

### Further tools
###### Firmware files:
- Bootloader file: boot_ra_Release.srec
- Controller Application: RA_APP_REL_6670771D.bin

###### Battery Control
Under */usr/share/jupiter_controller_fw_updater/RA_bootloader_updater/linux_host_tools*

you will find the BatCtrl program. It can be used to power cycle the controller.

`sudo ./linux_host_tools/BatCtrl SetCBPower 0`

turns the USB Power off for the controller board

`sudo ./linux_host_tools/BatCtrl SetCBPower 1`

turns USB Power on

###### Commands to make the programs executable
 chmod u+x "linux_host_tools/BatCtrl"
 chmod u+x "linux_host_tools/rfp-linux-x64/rfp-cli"

### Dumping the controller firmware
###### Using/modifying the flashing script.
I re-wrote chunks of the script under

- /usr/share/jupiter_controller_fw_updater/RA_bootloader_updater/rfp_cli_linux.sh*

to run my own commands.

###### Dumping the firmware:
![Figure. 1: Motorola SREC file. relevant Firmware marked yellow](images/2/25/Fig._1.jpg)
Set the controller board to USB boot mode as described here: [Steam Deck - Flash MCU on controller board R rev. B](Steam_Deck_-_Flash_MCU_on_controller_board_R_rev._B.md)

Connecting the MD pin to ground is a easy way to do it.

To dump the firmware, you can simply use the following command:

`sudo ./rfp-cli -d RA -port /dev/serial/by-id/usb-Renesas_RA_USB_Boot-if00 -read dump.srec`

The firmware will be dumped in the Motorola SREC format.

### Import the firmware
#### The easy way:
Import the firmware file into a Hex Editor like HxD. HxD can import SREC files.

#### The hard way (do not do this, just import into HxD):
###### Motorola SREC format
Read this: *https://en.wikipedia.org/wiki/SREC_%28file_format%29*
![Figure 2: Notepad ++ Wrong SREC Checksum](images/1/1a/Fig._2_Notepad_++_Wrong_SREC_Checksum.jpg)
The chart on the top right of the wikipedia page should explain the format it sufficiently.

##### Open the SREC File (in Notepad++)
Set the language of the file to Motorola SREC.

(see Figure 1): The blue characters (of the first 12 characters) are the Hex-address, the code is written to.

The numbers in the middle (figure 1, yellow) are the firmware.

The last two characters are the checksum. It has to be correct, in order to be written by the CLI tool

Notepad++ is useful for this. It tells you, if the checksum is wrong. (Figure 2)![Figure 3. Trimming the SREC file part 1](images/e/e6/Fig._3.jpg)
###### Trim the firmware file
You can use Notepad++ to cut out irrelevant parts. In the "search/replace" mode switch to "regular expressions".

Delete the first line and the last line. It is just a comment.

In the replace function type `(.{2})$` to replace the last two characters (Figure 3)

Type `^.{12}(.*)` into „search for“ and `\1` into „replace with“ to cut the first 12 characters (Figure 4).

The result should look like Figure 5.![Figure 4. Trimming the SREC file part 2](images/5/5f/Fig._4.jpg)

### Edit the firmware
![Figure 5. Trimmed SREC file](images/5/5b/Fig._5.jpg)![Figure 6: Controller firmware in HxD](images/3/3c/Fig._6.jpg)
Load the firmware into a hex editor like HxD (Figure 6)

At the beginning, there is the bootloader area (see boot_ra_Release.srec).

Between 0x00008000 and 0x00040000 sits the application data (see RA_APP_REL_6670771D.bin).

Between 0x08000000 and 0x08002000 there is provisioning and calibration data.

There is also some other data. I have not figured out what is what.

When you are done, either convert the file to the SREC format or flash the MCU with a bin file.

`sudo ./rfp-cli -d RA -port /dev/serial/by-id/usb-Renesas_RA_USB_Boot-if00 00000000 data.bin`

The command above should work. I have not tested this yet.

You can also write parts of the firmware to the MCU. Read the documentation.

## Happy modding.
