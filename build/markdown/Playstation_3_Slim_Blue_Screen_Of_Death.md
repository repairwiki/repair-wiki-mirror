---
title: "Playstation 3 Slim Blue Screen Of Death"
pageid: 4708
revid: 7790
kind: repair_guide
source: "https://repair.wiki/w/Playstation_3_Slim_Blue_Screen_Of_Death"
history: "https://repair.wiki/index.php?title=Playstation_3_Slim_Blue_Screen_Of_Death&action=history"
permalink: "https://repair.wiki/index.php?oldid=7790"
last_edited: "2025-06-18T22:12:02Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Playstation 3 Slim"
  - "Stubs"
infobox:
  Device: "Playstation 3 Slim"
  Affects_parts: "Motherboard"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Playstation 3 Slim Blue Screen Of Death

## Problem description
Console Turns on but after a few seconds it displays a blue screen saying "Settings information is corrupted"
![Error displayed](images/b/bf/Ps3_bsod.jpg)

## Symptoms
- Console Turns on but after a few seconds it displays a blue screen saying "Settings information is corrupted"

## Solution
This issue is usually related to a problem on the LAN section of the motherboard, this can be caused by a damaged LAN Port, LAN controller (88E1118R-NNC2) or a short on this circuit.

### Diagnostic Steps
The first step is to inspect the Ethernet Port for any physical damage or liquid damage.

The next step is to use a multimeter to check for shorts around the Ethernet controller, this component is located behind the LAN port.
![PS3 Lan Controller Location](images/7/76/Lan_controller_location.png)

it is common to find shorts here and it usually is the controller that is faulty.

### Repair Steps
If there is any physical damage to the LAN Port you can replace it or even remove it if you don't use it.

If there are shorts around the "Marvell" IC, you can inject a small amount of current into that circuit with a DCPS and see what gets hot. If there are shorts on multiple lines around the IC, it is probably the chip that is dead, this is a really common issue and in most cases it's the actual fault.

There are multiple versions of this component and to replace it you need to check markings on yours and make sure you get the same one.

![PS3 Lan controller Markings](images/5/55/PS3_Lan_controller_Markings.png)
This component may be hard to find to buy since the consoles are quite old now, so you may need to source from a donor board.

Replacing this component is quite straightforward simply use your heatgun to desolder the old IC, clean the old solder, add new solder, and use your heatgun to install the new IC.

#### Final Testing
After replacing the port or the LAN controller, make sure to plug an Ethernet cable and make sure the connection is able to connect to the internet.
