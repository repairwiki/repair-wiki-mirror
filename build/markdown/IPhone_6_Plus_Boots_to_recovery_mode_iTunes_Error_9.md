---
title: "IPhone 6 Plus Boots to recovery mode iTunes Error 9"
pageid: 4292
revid: 7378
kind: repair_guide
source: "https://repair.wiki/w/IPhone_6_Plus_Boots_to_recovery_mode_iTunes_Error_9"
history: "https://repair.wiki/index.php?title=IPhone_6_Plus_Boots_to_recovery_mode_iTunes_Error_9&action=history"
permalink: "https://repair.wiki/index.php?oldid=7378"
last_edited: "2025-06-05T20:06:07Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone 6 Plus"
  - "Stubs"
infobox:
  Device: "IPhone 6 Plus"
  Affects_parts: "Motherboard"
  Needs_equipment: "Soldering Iron, Hot-Air Station, Microscope, Multimeter"
  Type: "Soldering"
  Difficulty: "4. Specialist"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 6 Plus Boots to recovery mode iTunes Error 9

## Problem description
On the iPhone 6 Plus this error is usually a problem between the CPU and EEPROM (U0301)

![iTunes error 9](images/6/69/Itunes_erro_9.jpg)

## Symptoms
- The phone boots straight into recovery mode

- iTunes produces the error 9 when restoring the device

## Diagnostic Steps
In order to verify that in fact the issue is between the CPU and EEPROM we must take diode readings on two resistors, these two components are located under a shield, in order to reveal them you must remove a tiny bit of metal in the position of the image below.

![iPhone 6 Plus EEPROM location](images/3/34/IPhone_6_Plus_EEPROM_location.png)
The next step is to measure the two resistors in diode mode, they both must have a value of around 0.484, on some devices both lines will read bad and on some devices only one is faulty.
![iPhone 6 plus EEPROM Resistors](images/f/f6/IPhone_6_plus_EEPROM_resistors.png)

### Repair Steps
  - This repair is really difficult and is not advised for people without experience please practice on a scrap board  first.**

These two lines go to the CPU and "easiest" way to fix it is by making a small hole in the CPU.

Start by removing the metal shield on top of the CPU.

Next we will make a small hole in the bottom left corner of the CPU, below is an image of the area that can be cut.
![iPhone 6 Area that we can cut from the CPU](images/7/7c/IPhone_6_Area_that_we_can_cut_from_the_CPU.png)
To make the hole there are two tools that can be used a X-Acto knife or a small precision tool like the Qianli DM360.

Do this process really slowly and if you want you can add some isopropyl alcohol to help clear the debris and you will also see your work better.

At some point you will arrive at some grey pads, this means that you're getting close, keep scraping really slowly.
![iPhone 6 Plus RAM Pads](images/3/3c/IPhone_6_Plus_RAM_Pads.png)
After you scrape a little bit you will start to see the line inside the CPU, the two lines that we are after are these ones.

![iPhone 6 Plus CPU Lines](images/1/10/IPhone_6_Plus_CPU_Lines.png)
After locating these two lines stop scraping and use UV mask to cover everything in that area except those lines, like this:
![iPhone 6 Plus uv mask](images/c/c9/IPhone_6_Plus_uv_mask.png)
After applying UV mask add solder to those two exposed pads.

Now you need to solder 2 jumoing wires from those 2 points to the resistors.
![IPhone 6 Plus Jumper wires error 9.png](images/5/52/IPhone_6_Plus_Jumper_wires_error_9.png)
After soldering the wires check for a short on PP1V8_SDRAM you can do this on this cap.
![1v8 Ram iPhone 6 Plus.png](images/2/21/1v8_Ram_iPhone_6_Plus.png)
After confirming there is no short, protect the jumping wires with UV mask, you can basically cover the hole you made.

After this, connect the iPhone to iTunes again and do a restore.

Don't forget to install the metal shield on top of the CPU.
