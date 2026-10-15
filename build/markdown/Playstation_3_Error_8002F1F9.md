---
title: "Playstation 3 Error 8002F1F9"
pageid: 4091
revid: 14296
kind: repair_guide
source: "https://repair.wiki/w/Playstation_3_Error_8002F1F9"
history: "https://repair.wiki/index.php?title=Playstation_3_Error_8002F1F9&action=history"
permalink: "https://repair.wiki/index.php?oldid=14296"
last_edited: "2026-10-15T21:38:37Z"
contributors:
  - "Tiago199988"
  - "Nadaman"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for PlayStation 3 Super Slim"
  - "Repair guides for Playstation 3 Slim"
  - "Stubs"
infobox:
  Device: "Playstation 3 Slim, PlayStation 3 Super Slim"
  Affects_parts: "Motherboard"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-10-15"
generated: true
---

# Playstation 3 Error 8002F1F9

## Problem description
This error happens when the console is unable to detect the Wi-Fi/Bluetooth Module.
![Error 8002F1F9](images/f/ff/8002F1F9.jpg)

## Symptoms
- You try to update the console firmware and get error 8002F1F9.
- You can't use Wi-Fi or Bluetooth.

## Solution
This issue is caused by a design flaw where the PS3 is always providing power to the Wi-Fi module even with the console on standby, so that users can turn on the PS3 with the wireless controllers or Blu-ray remote. It causes the switching regulator to overheat, which then causes the 5V rail to be shorted onto the 1.8V rail. This can potentially damage the console's Wi-Fi/Bluetooth board.

The solution is to either replace the chip or do a small modification to the circuit by installing a different IC.

### Diagnostic Steps
On the Playstation 3 Slim or Super Slim, this problem is usually caused by a faulty switching regulator (marked with the diagrams below) where it fails to output 1.8V.

Below are the required voltages for the chip to work; start by measuring the voltage input of the chip. It must have 5V and 3.3V with the console on standby; if these 2 voltages are present, measure the output on the coil; it must be 1.8V.

![CECH-25xx Switching Regulator Voltages](images/c/cb/PS3_Slim_Wifi_1.8V.png)

### Repair Steps
There are two ways to repair this fault, you can either source a compatible 6-WDFN switching regulator (such as an [https://www.digikey.com/en/products/detail/richtek-usa-inc/RT8057GQW-2/4146466 RT8057]) and replace it (keeping in mind that with time it may fail again), or you can do a small modification by installing a [https://www.digikey.pt/en/products/detail/evvo/AMS1117-1-8/24370064 AMS1117-1.8], along with a 10 nf 6.3V MLCC.

#### Installing another 6-WDFN switching regulator
If you choose to install another switching regulator, the process is fairly simple.

Use your hot air station to desolder the old IC, clean the pads on the motherboard, add new solder, and solder the new chip where the old one was.

#### Installing the AMS1117-1.8
This solution may seem more complex, but it is better since the AMS1117 is a more reliable IC compared to the original switching regulator.

Due to the size of the AMS1117-1.8, you wont be able to install it in the position of where the original switching regulator is located.

##### CECH-25xx
1. Use your hot air station to remove the original switching regulator.
1. Solder the AMS1117-1.8 like the image below.
![667x667px](images/0/07/Cech25xx_regulator_fix_example.png)

##### CECH-30xx
1. Use your hot air station to remove the original switching regulator.
1. Solder the AMS1117-1.8 & a 10 nf MLCC like the image below.
1. After soldering the new AMS1117-1.8, make sure you have 1.8V on the middle pin.

![1000x1000px](images/0/0d/Cech30xx_regulator_fix.png)

## Final Testing
Reassemble the console and make sure you are able to update the console without any issues.

Make sure you can sync a controller using Bluetooth.

Connect your console to the internet using Wi-Fi.
