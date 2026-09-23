---
title: "MacBook Air A1932 No display backlight repair"
pageid: 167
revid: 3271
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Air_A1932_No_display_backlight_repair"
history: "https://repair.wiki/index.php?title=MacBook_Air_A1932_No_display_backlight_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3271"
last_edited: "2024-01-29T22:17:10Z"
contributors:
  - "ASRepairs"
  - "KevinShort"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Air A1932"
  - "Stubs"
infobox:
  Device: "MacBook Air A1932"
  Affects_parts: "Motherboard, Display assembly"
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera"
  Type: "Soldering, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Air A1932 No display backlight repair

## Problem description
Identifying and solving backlight issues on the *820-01521* logic board, as well as similar boards from 2016-2020. A MacBook with no backlight on the display is experiencing an issue where the screen remains dark even though the computer is powered on and operational. This means that while the computer itself may be functioning, the display is not emitting any light, making it extremely difficult or impossible to see the content on the screen. Shining a strong light on the display at an angle might reveal that the content is indeed present, but the backlight is not illuminating it.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- The display appears completely dark, with no visible content or backlight illumination.
- Occasionally, the backlight might flicker or flash briefly when the MacBook Pro is powered on or waking from sleep, but it remains dark after these brief instances.
- Connecting the MacBook Pro to an external monitor or TV results in a functional display on the external screen, confirming that the computer itself is working correctly.

## Solution
### Diagnostic Steps
#### Check for a short to ground on backlight output PPVOUT_LCDBKLT_F
- C8469 or adjacent capacitors in the series is an appropriate area to measure, since it does not require removal of the system board.
  - If a short to ground is measured, unplug the display connector to rule out a potential short to ground within the TCON board or LED strip of the display.
  - If the short is persistent with the screen unplugged, proceed to the "Backlight output shorted to ground" repair steps below.
#### Test with Known Working Display
- If no short is found and there's no liquid damage history, test with a known working display.
- If backlight works, proceed to "Device has backlight output on a known good display, but not on the originally installed display" steps.
#### Check U8400 and its circuit
Failure of U8400 without the presence of liquid damage is uncommon, however if you have no backlight with a known good display, and do not have a short on backlight output, U8400 may be bad or you may have another circuit fault such as a bad resistor or broken trace within the U8400/backlight generation circuit.

It is also common for current sensing pins (pins 9 and 10) of U8400 to be very corroded with corresponding pad/trace damage. If this is the case, run a wire for each pad and connect them to U5620 (Which is a omitted/no-stuff component.) Pin 9 (ISNS_LCDBKLT_N) can be run to Pin 5 of U5620 and Pin 10 (ISNS_LCDBKLT_P) can be run to pin 4 of U5620.
- Examine U8400 if corroded along with adjacent corroded components.
- Ensure that the backlight circuit has its input voltage (VIN) by measuring on BOTH SIDES of F8400 (Figure 3), which is the backlight fuse.
  - Voltage on both sides of the fuse should be equivalent to PPBUS_G3H.
  - The backlight fuse can blow in response to a previous short to ground in the backlight circuit, or due to the screen being plugged in without the battery disconnected.
  - Rarely, the backlight fuse can become open (blown) due to development of sulfur deposits on the fuses' filament , or due to micro manufacturing defects on the fuses filament.
  - If the backlight fuse is blown, check for a short on backlight output (PPVOUT_S0_LCDBKLT_F) and on backlight input (PPVIN_S0SW_LCDBKLT_F). If the fuse is blown, proceed to the "Backlight fuse (F8400) blown in the absence of a short to ground" repair steps below If voltage is normal on both sides of the backlight fuse, proceed to the next step.
- Check that the backlight circuit is being enabled. The screen will need to be connected for the enable signal to be sent out.
  - With the board on your bench, with a known good screen connected, measure voltage on pins 1 and 2 of R8442.
  - You should have ~3.3v. Low voltage (less than 3.3v but more than 0v) on pin 2 of R8442 (Figure 4) is suggestive of an issue with U8400.
  - If you have 0v on pin 1 of R8442, the backlight circuit is not being told to turn on, which raises the possibility of a CPU issue, or an issue with the display cable/connector.
- Check the 5v inputs to U8400 PP5v_S0_BKLT_D
  - PP5v_S0_LCDBKLT_D can be measured on R8444.
  - Be sure to check voltage on both sides of the resistor. If voltage is lower on one side of the resistor, R8444 or R8445 is likely blown, probably due to a short within U8400.
  - If PP5v_S0_LCDBKLT_D is low (Substantially lower than 5v), replace U8400 AND R8444 as R8444 acts as a current limiting resistor to protect PP5v_G3S, and likely blew as a result of an internal short within U8400.
      - If you have low voltage on pin 2 of R8442 with normal voltage on pin 1 of R8842, replace U8400.**
      - If VIN, EN, and PP5v_S0_LCDBKLT_D are all present at normal levels, and you do not have backlight, replace U8400.**
- If EDP_BKLT_EN is missing, U8400 is **NOT** the cause of the issue.
### Repair Steps
#### Backlight Output Shorted to Ground
- Identify and replace the shorted component.
- Check with and without the display connected. A short is commonly caused by a shorted capacitor.
- Inject 10v at 5 amps, thermally image the board, or use comparable short detection methods.
#### Device has Backlight Output on Known Good Display, But Not on Originally Installed Display
- Replace the display assembly.
- To retain keyboard backlight function, be sure to use the same year display.
#### Backlight fuse (F8400) blown in the absence of a short to ground
- Replace the backlight fuse with a fuse from a donor board or a compatible replacement.
  - 0603 package size, 3 amp, 32v fuse. Brand does not matter.
- Before applying power be sure to double check for a short to ground. Check for a short to ground on backlight output and backlight input*.
