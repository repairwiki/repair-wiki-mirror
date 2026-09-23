---
title: "Nintendo Switch Error Code: 2101-0001 Repair"
pageid: 929
revid: 2288
kind: repair_guide
source: "https://repair.wiki/w/Nintendo_Switch_Error_Code:_2101-0001_Repair"
history: "https://repair.wiki/index.php?title=Nintendo_Switch_Error_Code:_2101-0001_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=2288"
last_edited: "2024-01-13T20:31:34Z"
contributors:
  - "ASRepairs"
  - "HaileyKitty"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Nintendo Switch"
infobox:
  Device: "Nintendo Switch"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Nintendo Switch Error Code: 2101-0001 Repair

This article is a stub. You can help Repair Wiki grow by expanding it

## Problem description
The 2101-0001 error code for the **Nintendo Switch** can be pretty annoying, but it's usually pretty easy to diagnose and repair. This very specific error code is a critical error code related to a communication issue between the Nintendo Switch software and M92T36, the power management IC for the Switch. The very first thing to do, regardless of whether or not you see any kind of damage is to lift off the USB-C port. Replacing the port can cost about $1 on AliExpress, and since this issue is occurring, it's best to change the port regardless.

  - Remember, the USB-C port on the Nintendo Switch has a hidden row of pins. BE CAREFUL! Trace repair on the Nintendo Switch port is no easy task, and damage is easy to do. To put it into context, watch this video: [https://www.youtube.com/watch?v=HGEpVUnlGUM&t=2575s Nintendo Switch USB-C Trace Repair]**

There's also a [https://www.youtube.com/watch?v=JMkf45jV3H4 very detailed repair video] you can watch if you do not want to follow this guide

## Symptoms
- Error Code: 2101-0001

## Solution
This error code is generally caused by M92T36. 2101-0001 is an error on the i2c bus. This is a faulty M92 in **MOST** cases. There are cases where it can be something such as a faulty charging cable, excessive force, or accidental damage when inserting and removing the charging cable. It is not usually an error that will just occur on its own for no reason. Because this is a hardware-related (critical) error code, replacing components is your only option.

This error code is generally caused by M92T36. 2101-0001 is an error on the i2c bus.

This error code can be caused by the user inserting the cable incorrectly (on a strange angle).

This error code can be caused by faulty accessories, such as a damaged charging cable or dock.

This error code can be caused by some poorly created 3rd party USB-C accessories which lack proper circuit protection.

### Diagnostic Steps
Once the port is removed, proceed by testing the capacitors on M92T36 for shorts to ground using either diode or continuity mode on your multimeter. If there are no shorts, you may just have a port problem, so solder a new port and test. If you find shorts on M92T36, replace that IC. 2101-0001 is almost always both a port and IC problem. Even if you do have what appears to be a good M92T36, you may still have a problem with it. M92T36 doesn't always show obvious signs that it has developed a fault.

While you still have the motherboard out of the chassis, check for shorts on P13USB on the other side of the motherboard (Side-A). If the top capacitor has a short, remove and replace P13USB too.

Once M92T36, P13USB or both have been replaced you can test the console before installing a new port should you prefer. That is usually my preferred option.

### Repair Steps
The safest method I've personally found for removing the USB-C port is to remove any nozzle you have on your hot air wand. Use 480 degrees Celsius at around 40%(40l) air flow and hold the wand directly above the port from a straight angle. After around 60 seconds you will notice the lead-free solder will begin to melt. **Do not lift the port yet!** Start to lightly tap the port with a pair of tweezers while still applying heat until the port moves freely. Wait another 5-10 seconds after free movement starts and then slowly lift off the port. This might seem overkill, but spending an extra 30-60 seconds now will save you 60-90 minutes of work afterwards. **Do not bend the board, do not yank on the port, do not try and force it off. Take extra care, and save yourself a whole world of pain... I've seen it happen!**

Take extra care when removing the USB-C port.

Change the USB-C port anyway, regardless of how it looks.

Always clean the inside of the port using something soft, such as a small cotton swab or soft tooth brush after installation. It will always have flux inside.

Always clean all flux residue from the motherboard after component-level work. Leaving flux residue could potentially corrode the motherboard over time.

Ensure the console will charge using both an official Nintendo Switch charger (15v) and a 5v standard charger on **both** sides of the port (flip the cable around)

Ensure the console docks to the TV after replacing the port. If it doesn't, it might not be installed correctly. Usually reflowing the port will correct this.

Ensure the console bumps up to fast charging after repair.

Do a full system test after repair including display, audio, charging, power, docking, joycon connectivity (wired and wireless), Wi-Fi connectivity, touch screen functionality, game reading and playing (using a game cartridge, not digital download)

If you are a repair shop, advise your customer to replace their charging cable too. Failing to replace the cable may result in the device coming back under warranty when the customer's faulty accessories break it again

For a detailed video guide, refer to the video above.
