---
title: "How to use ODIN to flash firmware on Samsung devices"
pageid: 6745
revid: 13892
kind: explanatory_guide
source: "https://repair.wiki/w/How_to_use_ODIN_to_flash_firmware_on_Samsung_devices"
history: "https://repair.wiki/index.php?title=How_to_use_ODIN_to_flash_firmware_on_Samsung_devices&action=history"
permalink: "https://repair.wiki/index.php?oldid=13892"
last_edited: "2026-02-08T21:24:49Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for Galaxy A03s"
  - "Explanatory guides for Galaxy A05s"
  - "Explanatory guides for Galaxy A10e"
  - "Explanatory guides for Galaxy A12"
  - "Explanatory guides for Galaxy A13 4G"
  - "Explanatory guides for Galaxy A13 5G"
  - "Explanatory guides for Galaxy A14 5G"
  - "Explanatory guides for Galaxy A15"
  - "Explanatory guides for Galaxy A15 5G"
  - "Explanatory guides for Galaxy A20e"
  - "Explanatory guides for Galaxy A23"
  - "Explanatory guides for Galaxy A3"
  - "Explanatory guides for Galaxy A32"
  - "Explanatory guides for Galaxy A32 5G"
  - "Explanatory guides for Galaxy A33 5G"
  - "Explanatory guides for Galaxy A41"
  - "Explanatory guides for Galaxy A51"
  - "Explanatory guides for Galaxy A52s 5G"
  - "Explanatory guides for Galaxy A53 5G"
  - "Explanatory guides for Galaxy A54 5G"
  - "Explanatory guides for Galaxy A71"
  - "Explanatory guides for Galaxy A72"
  - "Explanatory guides for Galaxy Note 10"
  - "Explanatory guides for Galaxy Note 10 Lite"
  - "Explanatory guides for Galaxy Note 10 Plus"
  - "Explanatory guides for Galaxy Note 20"
  - "Explanatory guides for Galaxy Note 20 Ultra"
  - "Explanatory guides for Galaxy Note 8"
  - "Explanatory guides for Galaxy Note 9"
  - "Explanatory guides for Galaxy S10"
  - "Explanatory guides for Galaxy S10 Plus"
  - "Explanatory guides for Galaxy S20"
  - "Explanatory guides for Galaxy S20 FE"
  - "Explanatory guides for Galaxy S20 Plus"
  - "Explanatory guides for Galaxy S20 Ultra"
  - "Explanatory guides for Galaxy S21"
  - "Explanatory guides for Galaxy S21 FE"
  - "Explanatory guides for Galaxy S21 Plus"
  - "Explanatory guides for Galaxy S21 Ultra"
  - "Explanatory guides for Galaxy S22"
  - "Explanatory guides for Galaxy S22 Plus"
  - "Explanatory guides for Galaxy S22 Ultra"
  - "Explanatory guides for Galaxy S23"
  - "Explanatory guides for Galaxy S23 Ultra"
  - "Explanatory guides for Galaxy S24 Ultra"
  - "Explanatory guides for Galaxy S25"
  - "Explanatory guides for Galaxy S25 Edge"
  - "Explanatory guides for Galaxy S25 FE"
  - "Explanatory guides for Galaxy S25 Plus"
  - "Explanatory guides for Galaxy S25 Ultra"
  - "Explanatory guides for Galaxy S7"
  - "Explanatory guides for Galaxy S8"
  - "Explanatory guides for Galaxy S9"
  - "Explanatory guides for Galaxy Tab A8"
  - "Explanatory guides for Galaxy Tab S3"
  - "Explanatory guides for Galaxy Tab S6"
  - "Explanatory guides for Galaxy Tab S8 Plus"
  - "Explanatory guides for Galaxy Tab S9"
  - "Explanatory guides for Galaxy XCover 6 Pro"
  - "Explanatory guides for Galaxy Z Flip 4"
  - "Explanatory guides for Galaxy Z Fold 4 5G"
  - "Explanatory guides for Tab A7 Lite"
  - "Explanatory guides for Tab S7 FE"
  - "Missing device page"
infobox:
  Type: "Troubleshooting/Diagnostics"
  Device: "Galaxy A03s, Galaxy A10e, Galaxy A12, Galaxy A13 4G, Galaxy A14 5G, Galaxy A15 5G, Galaxy A20e, Galaxy A23, Galaxy A3, Galaxy A32, Galaxy A32 5G, Galaxy A33 5G, Galaxy A41, Galaxy A51, Galaxy A52s 5G, Galaxy A53 5G, Galaxy A54 5G, Galaxy A72, Galaxy Note 10, Galaxy Note 10 Lite, Galaxy Note 10 Plus, Galaxy Note 20, Galaxy Note 20 Ultra, Galaxy Note 8, Galaxy Note 9, Galaxy S10, Galaxy S10 Plus, Galaxy S20, Galaxy S20 FE, Galaxy S20 Plus, Galaxy S20 Ultra, Galaxy S21, Galaxy S21 FE, Galaxy S21 Plus, Galaxy S21 Ultra, Galaxy S22, Galaxy S22 Plus, Galaxy S22 Ultra, Galaxy S23, Galaxy S23 Ultra, Galaxy S24 Ultra, Galaxy S7, Galaxy S8, Galaxy S9, Galaxy XCover 6 Pro, Galaxy Z Flip 4, Galaxy Z Fold 4 5G, Galaxy A05s, Galaxy A13 5G, Galaxy A15, Galaxy A71, Galaxy S25, Galaxy S25 Edge, Galaxy S25 FE, Galaxy S25 Plus, Galaxy S25 Ultra, Galaxy Tab A8, Galaxy Tab S3, Galaxy Tab S6, Galaxy Tab S8 Plus, Galaxy Tab S9, Tab A7 Lite, Tab S7 FE"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How to use ODIN to flash firmware on Samsung devices

## What is ODIN?
Odin is a leaked official tool to flash firmware onto Samsung Phone and Tablets.

## Why is this tool useful?
This tool and help us to restore or update the firmware of the device in case it gets corrupted.

With this software we can sometimes repair devices that are bootlooping, of stuck on Samsung logo.

## Software needed:
ODIN: https://xdaforums.com/t/patched-odin-3-13-1.3762572/

SamKey(will explain later on the guide why this is needed): https://www.samkey.org/

## Step 1: Download and Prepare ODIN
1. Download the ODIN ZIP file from a verified source (e.g., the patched version linked above).
1. Extract the ZIP: Right-click > "Extract All" > "Extract."
1. Open ODIN: Run the .exe file (it has a large logo). Click "OK" on any security prompts.

ODIN's interface includes slots for firmware files (BL, AP, CP, CSC), a Log window, Options tab, and PIT tab.

## Step 2: Identify Your Device's Details
1. Boot your device into Download Mode, If you dont know how simply google: How to place [Insert your device here] into download mode
1. Connect the device to your PC via USB.
1. Open SamKey and click "Read Info D/L." Note the:
1. * Device Model (e.g., SM-G990B2).
1. * Version (firmware build).
1. * Carrier/CSC
![660x660px](images/b/b7/Samkey_info.png)
If the device won't enter Download Mode, ODIN can't help—suspect hardware issues like CPU or eMMC failure.

## Step 3: Download Firmware
1. Go to samfw.com
1. Enter your device model, select your CSC/region, and match the version from Step 2.
![702x702px](images/4/40/Samfw.png)

## Step 4: Load Files into ODIN
1. In ODIN:
1. * ![Home csc.png](images/e/e5/Home_csc.png)**BL**: Insert the Bootloader file (BL_ prefix). Loads system files and Android.
1. * **AP**: Insert the Android Processor file (AP_ prefix). Flashes to /system partition (largest file, takes longest).
1. * **CP**: Insert the Core Processor file (CP_ prefix). For modem/radio images.
1. * **CSC**: Insert the CSC file for region/carrier changes. !!!**VERY IMPORTANT!!!** **Use HOME_CSC_ to keep data (no wipe); regular CSC_ wipes data for a clean install.**
1. ODIN should detect your device (COM port lights up blue).
![ODIN Should look like this when all the files are imported](images/0/0a/Odin_Ready.png)

## Step 5: Flash the Firmware
![Odin pass.png](images/6/65/Odin_pass.png)
1. Ensure device is in Download Mode and connected.
1. Click "Start" in ODIN
1. Monitor the Log window for progress. It ends with "PASS!" (green) on success or "FAIL!" (red) on error.
1. Device reboots if Auto Reboot is checked.
