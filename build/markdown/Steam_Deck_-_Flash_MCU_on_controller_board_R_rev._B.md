---
title: "Steam Deck - Flash MCU on controller board R rev. B"
pageid: 2346
revid: 4952
kind: repair_guide
source: "https://repair.wiki/w/Steam_Deck_-_Flash_MCU_on_controller_board_R_rev._B"
history: "https://repair.wiki/index.php?title=Steam_Deck_-_Flash_MCU_on_controller_board_R_rev._B&action=history"
permalink: "https://repair.wiki/index.php?oldid=4952"
last_edited: "2024-10-03T16:49:01Z"
contributors:
  - "ASRepairs"
  - "DawidMurawski"
  - "Stanto"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Steam Deck"
infobox:
  Device: "Steam Deck"
  Affects_parts: "Controller board revision B; R7FA4E10B2CFM; R7FA4E10D2CFM"
  Needs_equipment: "Steam Deck LCD"
  Type: "Software"
  Difficulty: "1. Easy"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Steam Deck - Flash MCU on controller board R rev. B

Steam Deck LCD - Flash MCU on controller board "R" revision B (Renesas RA4E1 MCU - R7FA4E10B2CFM or R7FA4E10D2CFM)

## Problem description
The controller board is not detected by SteamOS; MCU of the controller board was replaced and needs to be flashed with firmware
## Symptoms
- The controller board is not detected by SteamOS
- The MCU needed to be replaced and flashed

## Solution
There are three options to program the MCU on the controller board revision B.

Option 1: Flash the MCU off-the-board via external circuit and mount the MCU on the controller board afterwards.

Option 2: Flash via external programmer and tag-connect cable (TC2050)

Option 3: Program the MCU in USB boot mode via Steam OS

You can use the R7FA4E10B2CFM (256 KB flash) or the R7FA4E10D2CFM (512 KB flash) MCU on the revision B controller board.

### Repair Steps
![(optional) Figure 1: Connect the mode pin of the MCU to ground to switch to USB boot mode for programming](images/0/07/Mode_pin_connected_to_ground.webp)
  - Option 3: Program the MCU via USB via SteamOS**

To program the MCU via USB in Steam OS, we will need to either switch to Desktop mode (with e.g. external keyboard/mouse) or connect to the Deck via SSH (recommended way) from another computer. If you need to know how to switch to desktop mode or connect to SSH, check another guide.

Superseded by "magic button combo" (but useful for debugging or fiddling around with the controller board firmware): The RA4E1 MCU needs to be put into USB/Serial boot mode by pulling the mode pin (MD) to ground during reset/power-on and keeping it pulled down during programming.
![Figure 2: Pinout of the tag connect (TC2050) interface on the revision B controller board](images/9/90/TC2050_interface_pinout.webp)
  - Step 1 - prepare the controller board:** Power off the Steam Deck/put it into standby. Connect the MD (mode) pin to ground (see figure 1). You can connect two pads of the tag-connect interface (the two on the upper right) for this (see figure 2). Power on the Deck/wake from standby. Check if the MCU has booted in USB mode by typing `lsusb` in console. You should see the following device (see figure 3):
![Figure 3: lsusb: Renesas MCU in USB boot mode for programming](images/3/34/Lsusb-_Steam_Controller_bootloader.webp)
`Hitachi, Ltd RA USB Boot`

  - Step 2 - flash the bootloader:** Change directory:
![Figure 4: Running the script to flash the bootloader on the Renesas MCU via USB](images/0/0d/Flash_Renesas_MCU.webp)
`cd /usr/share/jupiter_controller_fw_updater/RA_bootloader_updater`

run the script:

`./rfp_cli_linux.sh boot_ra_Release.srec`

(see figure 4) The script will as you to press and *hold* "Right Bumper" (R1), "Right Upper Back" (R4) and "Right Quick Access" ("...") (-> the "magic button combo", can be skipped if MD-pin is connected to ground) . Keep the buttons pressed and programming will start. (The script will power cycle the controller board and the MCU on the controller board will boot up in programming mode, if it detects the magic button combo. You can find more info on this on the Renesas website). Keep the buttons pressed, until the script prompts you to release them. The script will end and the bootloader is flashed on the MCU. Confirm this by typing `lsusb` into the console. You should see a USB device called `Valve Software Steam Controller Bootloader`
![Figure 5: lsusb: Valve Software Steam Controller Bootloader](images/5/53/Lsusb-_Steam_controller_bootloader.webp)
  - Step 3 - tidy up:** Power down the deck. (Remove the connection between MD and ground, if applicable.) Reassemble the Steam Deck and power on. The MCU will be programmed by SteamOS during start up. Confirm this by typing `lsusb` into the console. You should see a device called `Valve Software Steam Controller` The controller should also be recognized in gaming mode. All controller inputs should work.

Done.

  - Note:** If a brand new MCU is flashed with the firmware, there is the issue, that the Steam Deck serial number and the Controller Serial Number is not recognized. Updates via Steam Overlay will not work. Updates via Desktop mode work. Everything else works. This is most likely a pairing issue. I have not worked this problem out, yet. Maybe a factory reset of SteamOS or a fresh install of SteamOS will fix this.
