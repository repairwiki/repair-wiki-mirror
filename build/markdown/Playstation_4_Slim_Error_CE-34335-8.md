---
title: "Playstation 4 Slim Error CE-34335-8"
pageid: 4103
revid: 7069
kind: repair_guide
source: "https://repair.wiki/w/Playstation_4_Slim_Error_CE-34335-8"
history: "https://repair.wiki/index.php?title=Playstation_4_Slim_Error_CE-34335-8&action=history"
permalink: "https://repair.wiki/index.php?oldid=7069"
last_edited: "2025-05-24T22:56:24Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Playstation 4 Slim"
  - "Stubs"
infobox:
  Device: "Playstation 4 Slim"
  Affects_parts: "HDD, Motherboard"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Playstation 4 Slim Error CE-34335-8

## Problem description
This happens when the console is unable to detect the Hard Disk.
![Error CE-34335-8](images/8/8e/CE-34335-8.jpg)

## Symptoms
- Console Boots and displays the error CE-34335-8

## Solution
On the PS4 Slim this Error can be caused by a faulty HDD or Faulty mosfet behind the Sata conector.(i've seen this multiple times on PS4 Slims).

### Diagnostic Steps
Try a new 2.5" HDD or SSD, if you still have the same error this is probably due to a missing voltage that goes to the Sata Connector.

Behind the Sata connector there is a 8 leg Mosfet (TPS2001D).

This mosfet if working should output 5V.

In order for the mosfet it needs to have 5V on the input and it must more than 2V on the Enable.

Bellow is a image with points to measure.

THESE VOLTAGES ONLY APPEAR WHEN THE CONSOLE IS TURNED ON
![TPS2001D Voltages](images/f/f8/TPS2001D.png)

### Repair Steps
This component is widedly available in websites like Mouser and Aliexpress.

Replacing the TPS2001D is fairly simple.

Use your Hot air station to desolder the old mosfet be careful to not melt the Sata Connector.

Clean the old solder and apply new solder.

Solder a new mosfet.

## Final Testing
After installing a new mosfet make sure you have 5V on the output.

Install the HDD and turn the console on check the general functionality.

If you are installing a new HDD follow the instructions on the Oficial Playstation Support page [https://www.playstation.com/en-us/support/hardware/ps4/system-software/]
