---
title: "IPhone 6S No Image"
pageid: 8188
revid: 13180
kind: repair_guide
source: "https://repair.wiki/w/IPhone_6S_No_Image"
history: "https://repair.wiki/index.php?title=IPhone_6S_No_Image&action=history"
permalink: "https://repair.wiki/index.php?oldid=13180"
last_edited: "2025-12-10T22:08:33Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone 6S"
  - "Stubs"
infobox:
  Device: "IPhone 6S"
  Affects_parts: "Motherboard"
  Needs_equipment: "Soldering Iron, Hot-Air Station, Microscope"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 6S No Image

## Problem description
The Device turns on but it has no image.
## Symptoms
- Device boots but no image is displayed

## Solution
The no image problem can have 2 causes a bad display or a motherboard problem.

### Diagnostic Steps
The first thing to do is to always rule out bad parts, so first try a new display on the phone if it works great all that is need is a screen replacement.

If even with a new display the phone is unable to display any image the problem is on the motherboard.

Start by inspecting the FPC connector for any liquid or physical damage.
![iPhone 6S LCD FPC](images/3/3e/Iphone_6s_lcd_fpc.jpg)
If everything is fine take diode readings of the display FPC and compare them with the image bellow.
![870x870px](images/b/be/IPhone_6S_Display_FPC_DIODE.png)

If the diode readings you took are ok next thing to check is if the voltages need to display image are present.
- PP5V7_LCM_AVDDH_CONN
- PN5V7_LCM_MESON_AVDDN_CONN
- PP1V8_LCM_CONN
- PP5V7_MESON_AVDDH_CONN

These voltages can be measured here and only show up with the device turned on.
![IPhone 6S Display Voltages.jpg](images/1/1b/IPhone_6S_Display_Voltages.jpg)
It is common to have a short circuit on one of these lines, most of these lines also have a filter that acts kinda like a fuse and may open if there is overcurrent.

A somewhat common issue is having C4002 shorted. To check this, set your multimeter to continuity mode and place a probe on each side of the capacitor. It should *not* show continuity.

![C4002 iPhone 6S.png](images/4/40/C4002_iPhone_6S.png)
If the voltages are present, the issue is likely on the MIPI lines. Most of these lines go straight to the CPU through a filter. If every filter is present and testing good, the fault is most likely within the CPU itself.

Here is a Block diagram of how the picture circuit works.

![600x600px](images/0/02/IPhone_6S_Display_Block_Diagram.png)

## Repair Steps
If by replacing by trying a new display the image fault is solved all you have to do its to replace the display.

If there is a any physical damage to the FPC the solution is to replace it. The best method is to use a hot air station to desolder the old FPC, clean the old solder from the motherboard, apply new solder, align the new FPC, and use the hot air station to solder it. Be careful not to use excessive heat, as you may cause a solder bridge under the motherboard.

When taking diode readings of the FPC, if you measure a line that should read, for example, 0.500V but get 0.100V or 0.000V, it indicates a short on that line. The best way to trace the short is to inject voltage into the line with a DCPS and use a thermal camera to identify which component heats up. Fallow this guide how to find the short [Short Circuits - Repair Basics](Short_Circuits_-_Repair_Basics.md)

If you measure a line that should read 0.500V but get OL (Open Line), it indicates a disconnection in the circuit. To trace the issue, consult the board view to follow the line’s path.

If you have to replace a Filter the best way is to use your hot air station with a low air speed or the component may fly away.

If any of the voltages are missing, use the block diagram to trace where the voltage is generated and replace the chip responsible for creating that voltage. These components are easily available online and are generally easy to find.

## Final Testing
After assembling the phone, ensure every function is working as expected, not just the display, there are a lot of small components around the LCD FPC and when heating this area sometimes you end up desoldering something by mistake.
