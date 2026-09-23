---
title: "IPhone 11 Always Searching for Network IMEI Present"
pageid: 4211
revid: 7212
kind: other
source: "https://repair.wiki/w/IPhone_11_Always_Searching_for_Network_IMEI_Present"
history: "https://repair.wiki/index.php?title=IPhone_11_Always_Searching_for_Network_IMEI_Present&action=history"
permalink: "https://repair.wiki/index.php?oldid=7212"
last_edited: "2025-05-29T21:56:07Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 11"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 11 Always Searching for Network IMEI Present

## Problem description
The iPhone is unable to get network service but IMEI is present when dialing *#06#.
![iPhone 11 With no Service](images/5/5e/IPhone_11_With_no_service.jpg)

## Symptoms
- The iPhone is unable to get network service but IMEI is present when dialing *#06#.
- The Phone is always searching for network.

### Diagnostic Steps
Start by opening the Phone app and dialing *#06#, and you see a window pop up with the IMEI.
![Example Modem firmware](images/5/5c/Example_Modem_firmware.jpg)
Go to the Settings app, General > About, scroll down, and check if Modem Firmware is present.

When this information is present, it already tells us that the Baseband CPU and Power Management Unit (PMU) are working.

The next step is to split the motherboard.

The first thing to check after splitting the boards is for any ripped pads, which is really common in phones that have suffered hard drops.

![Ripped Motherboard Pads](images/4/4a/Ripped_Motherboard_Pads.jpg)
Having ripped pads doesn't mean the problem is caused by them. If you find a ripped pad, you must check on a BoardView diagram what that trace or line does and if there are any other alternate points. For example, there are a lot of ground points, if you are missing a few, it’s unlikely that it will cause an issue.

The next thing to check is to compare the diode readings of specific pads with a known good board, or if you have a program like ZXW, you can check the values there, but generally, you want to check the lines or pads close to the network-related chips.

The Network circuit is devided into both motherboards the top board and bottom board.

![iPhone 11 Component Location](images/4/44/Iphone_11_component_location.jpeg)
After taking diode readings of the bottom board, shift focus to the top board. This is probably where the issue is.

Below are the diode readings around the network chips on the top board of the iPhone 11 series. It is common for the VFE_HI_3V15 line to get shorted.
![456x456px](images/f/f3/Iphone_11_top_board_network_diode_readings.jpg)
In order to locate the short on the VFE_HI_3V15, you must inject 1V into the line and monitor the temperature using a thermal camera of the capacitors and two ICs.

![Short on component](images/7/7a/Short_on_component.png)

### Repair Steps
After locating the short, simply replace the faulty component with a new one.

If you have a tool like an iSocket, test the motherboard before reballing it.

Reball the motherboard.

## Final Testing
After reballing the motherboard, insert a SIM card and ensure the phone is able to find a network.

Check if the 4G signal is good and stable.

Make a phone call.

Also, make sure to test every function of the device, since a bad solder joint on a pad between the top and bottom boards can sometimes occur.

Make sure the device doesn't randomly reboot.
