---
title: "IPhone 6 No Service Modem Firmware OK"
pageid: 5367
revid: 8595
kind: repair_guide
source: "https://repair.wiki/w/IPhone_6_No_Service_Modem_Firmware_OK"
history: "https://repair.wiki/index.php?title=IPhone_6_No_Service_Modem_Firmware_OK&action=history"
permalink: "https://repair.wiki/index.php?oldid=8595"
last_edited: "2025-07-07T22:25:49Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone 6"
  - "Stubs"
infobox:
  Device: "IPhone 6"
  Affects_parts: "Motherboard"
  Needs_equipment: "Microscope, Soldering iron, hot air gun"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 6 No Service Modem Firmware OK

## Problem description
The iPhone is unable get celular service
![iPhone 6 With No Service](images/9/94/No_service.jpg)

## Symptoms
- The iPhone is unable get celular service

## Solution
On the iPhone 6 this issue is ussualy caused by 2 broken pads under the Baseband CPU(V1 and U1)

### Diagnostic Steps
Confirming the fault go to settings and check if modem firmware is present if it is this means the Baseband PMU is working.

On the Dial app input the code ***#06#** a pop up window should show up with the IMEI of the iPhone.

Doing these steps confirms the fault is with the Baseband CPU
### Repair Steps
Diasamble the iPhone the Baseband CPU is located on the lower side of the motherboard under a EMI Shield, in order to acess the Baseband we have to remove this shield, on this part of the motherboard there is a lot of ground so it will take quite a bit of heat to remove it.
![iPhone 6 Baseband EMI Shield](images/b/bf/IPhone_6_Baseband_EMI_Shield.png)
After removing the shield the next step is to focus on the baseband CPU, unlike modern iPhones the baseband CPU on the iPhone 6 is not underfield, while the board is still hot using your hot air gun desolder the Baseband CPU and put it a side **but dont lose it.**
![iPhone 6 Baseband CPU](images/2/23/IPhone_6_Baseband_CPU.png)
While the board is hot from removing the Baseband add low melt solder to the pads on the motherboard then using solder wick clean the pads.

After cleaning the pads do a visual inspection it is common to remove a few pads in this process there are quite a few pads that are unused and come of easy. The pads with the color blue on the image bellow are fine if removed.
![iPhone 6 Baseband CPU Diode](images/2/20/IPhone_6_Baseband_CPU_Diode.png)
After completing your inspection lets focus on the V1 and U1 pads, these pads are common to break.

To repair the pads you need to do a small jump

First Scrape these points:

![Points to scrape](images/0/0b/Points_to_scrape.png)

Then add some solder and solder a thing of wire like this
![iPhone 6 V1 and U1 jump](images/d/da/IPhone_6_V1_and_U1_jump.png)

Then after this is done you can add a bit of solder mask to the points you scrape like this:
![Points covered in solder mask](images/a/ab/Points_covered_in_solder_mask.png)

After this is done you have to reball the Baseband CPU, you can not replace this component you have to reball it.

After reballing the Baseband solder the chip back on the board.

## Final Testing
After soldering the iPhone go to the dial app and insert once more the code *#06# and check for the pop up window with IMEI.

Insert a SIM card and make sure the iPhone is able to get service.

Make a phone call.

1.
