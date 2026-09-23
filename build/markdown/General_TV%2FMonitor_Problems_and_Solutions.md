---
title: "General TV/Monitor Problems and Solutions"
pageid: 1010
revid: 4661
kind: explanatory_guide
source: "https://repair.wiki/w/General_TV/Monitor_Problems_and_Solutions"
history: "https://repair.wiki/index.php?title=General_TV/Monitor_Problems_and_Solutions&action=history"
permalink: "https://repair.wiki/index.php?oldid=4661"
last_edited: "2024-08-20T16:39:17Z"
contributors:
  - "ASRepairs"
  - "HaileyKitty"
  - "ClassyPenguin"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for Television/Monitors"
  - "Missing device page"
  - "Television/Monitors"
infobox:
  Device: "Television/Monitors"
  Type: "Troubleshooting/Diagnostics"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# General TV/Monitor Problems and Solutions

| Problem | Solution |
| --- | --- |
| TV won`t power on. Standby LED blinking. |  * If the standby LED flashes, the problem is usually with the power supply. Check the diodes and capacitors as they are usually the cause of this behaviour. * Sometimes there can be a problem in the TV's firmware; in this situation it is necessary to reinstall the firmware and it is desirable to replace the EEPROM. |
| TV won't power on. Standby LED behaves as expected (on when the TV is off, then off when the TV is turned on) but the TV screen will remain off. |  * This is most likely a power supply fault. It could be a faulty capacitor. This symptom indicates that the TV has enough power for standby, but not for operation (especially the display, which consumes most of the power). A good troubleshooting step is to connect the TV's HDMI output to a device that can read the EDID information and see if any information is communicated via HDMI. |
| TV has sound but no image. Backlight not working. |  * May be that one or more LEDs in the backlight strip is broken, check each LED in the strip (start with 2.6V or 5.7V PSU, or use the diode check on a multimeter) you can replace the broken LED or replace the whole strip. * May be the PSU is the problem, if LED in strip is good, then LED driver or backlight capacitor in PSU unit, depending on manufacturer, there are kit components for LED driver in PSU unit. Take the multimeter to measure the capacitance of the capacitor compared to the marking. * May be the backlight inverter. Beware of the voltage it is designed to output, which can easily exceed 500V. Use appropriate equipment (at least 1000V rated) to test it. Test the transformer in continuity mode and in ohmic mode to isolate the short-circuit. * Check the Y driver board next to the LCD for burnt out buffer scan IC chips. These can overheat, particularly on older plasma TVs, and can be replaced. |
| No sound |  * Check the volume, sound settings, and cables. * Unplug the TV, press and hold the power button on the TV for 30 seconds, then plug it back in. * If the problem persists, check if an update is available for the television or reset the television to its factory default settings. * If the problem persists intermittently even after resetting to factory defaults, some TVs have a "quick start" (standby) mode option that doesn't turn off the TV when you press the power button, for a faster startup time. Change this setting to full shutdown. |
| TV stuck at Boot Logo or Black Screen |  * Some cheap TVs such as Grundig, Telefunken, Dyon, JTC and Kendo (Vestel mainboards) use a firmware that tends to self-destruct, try to find the correct firmware for the mainboard and flash it using an external programmer. * The problem can also be caused by cold solder joints or missing connections under the CPU. This is usually the case with Vizio TVs, where a reflow of the CPU can be repaired with hot air (approx. 3 minutes) or a high quality BGA station. |
