---
title: "How To Fix Nintendo Switch OLED With No HDMI Output"
pageid: 1879
revid: 4069
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_Nintendo_Switch_OLED_With_No_HDMI_Output"
history: "https://repair.wiki/index.php?title=How_To_Fix_Nintendo_Switch_OLED_With_No_HDMI_Output&action=history"
permalink: "https://repair.wiki/index.php?oldid=4069"
last_edited: "2024-06-13T11:44:16Z"
contributors:
  - "ASRepairs"
  - "VCCBoardRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Nintendo Switch OLED"
infobox:
  Device: "Nintendo Switch OLED"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "BGA, Soldering"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix Nintendo Switch OLED With No HDMI Output

## Problem description
Here's how to fix a Nintendo Switch OLED that has no HDMI output. When you plug in the device to the dock, the TV will not show anything.
![Figure 1. The Mechanic Readings of a Nintendo Switch OLED with No HDMI Output](images/6/6e/Nintendo_Switch_OLED_No_HDMI_Output_Mechanic_Readings.png)

## Symptoms
- No HDMI Output
- Dock not working
- TV Does not display anything from the Nintendo Switch
- Mechanic Reader shows Pin 8 and 17 as OL (Figure 1)

## Solution
![Check this choke when your Mechanic Readings show OL for pin Pin 8 and 17](images/a/a8/Nintendo_Switch_OLED_-_Pin_8_and_17_choke.png)
If you have Pin 8 and 17 as OL as shown in Figure 1, you most likely have a blown choke on that circuit.

It is located on the bottom side of the board, above the USB C port.

You'll need to check for continuity across the choke. View the visible traces, so you can see how the continuity should travel.

You can also diode mode each leg of the choke. All 4 legs should give you a diode mode reading.

If you get OL on the port side (lower) of the choke, but you get diode mode readings on the top side, then the choke is bad.

You can replace it from any other Nintendo Switch or Switch OLED. You can also often find them on other devices, like iPhones, iPads & other Android devices. They're often near the LCD/Display connector.

Once you replace the bad choke, you should no longer get OL through the mechanic reader & the Switch OLED should start displaying on the TV via HDMI.
![Known good Mechanic readings for Nintendo Switch OLED](images/5/5c/Switch_OLED_Mechanic_Readings.jpg)
