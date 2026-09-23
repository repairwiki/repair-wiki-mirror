---
title: "MacBook Air A2337 No backlight on display repair"
pageid: 67
revid: 463
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Air_A2337_No_backlight_on_display_repair"
history: "https://repair.wiki/index.php?title=MacBook_Air_A2337_No_backlight_on_display_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=463"
last_edited: "2023-10-29T15:21:09Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Missing device page"
  - "Repair guide"
  - "Repair guides for MacBook Pro A2337"
  - "Stubs"
infobox:
  Device: "MacBook Pro A2337"
  Affects_parts: "display board, main board"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Air A2337 No backlight on display repair

## Problem description
No backlight on display on the 820-02016 Logic Board, The laptop turns on, LCD is displaying a picture but without backlight.

## Symptoms
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
Detail all measurable or observable symptoms in this section.

- No Backlight
- All voltage rails are normal
- Possible liquid damage/corrosion

## Solution
### Diagnostic Steps
#### Failed display TCON board or a failed display LED strip
- Check for a short to ground on backlight output (PPVOUT_LCDBKLT)
  - CP860 or adjacent capacitors in the series is an appropriate area to measure, since it does not require removal of the system board.
  - If a short to ground is measured, unplug the display connector to rule out a potential short to ground within the TCON board or LED strip of the display.

#### Short to ground on backlight output caused by a failed output decoupling capacitor (Most common)
- Check for a short on the backlight output while the screen is unplugged
  - CP860 or adjacent capacitors in the series is an appropriate area to measure, since it does not require removal of the system board.
- If the short is persistent with the screen unplugged, proceed to the "Backlight output shorted to ground" repair steps below.

#### Failed backlight driver (UP800)
- UP800 is in a prime spot to be hit with liquid on the *820-02016* and is very commonly seen to be corroded after history of liquid damage.
  - Failure of UP800 without the presence of liquid damage is uncommon, however if you have no backlight with a known good display, and do not have a short on backlight output, UP800 may be bad or you may have another circuit fault such as a bad resistor or broken trace within the UP800/backlight generation circuit.
  - If UP800 is corroded, replace it along with any other corroded resistors or capacitors adjacent to it.
- It is common for current sensing pins (pins 9 and 10) of UP800 to be very corroded with corresponding pad/trace damage.
  - gently scrape the coating off of the traces going to pins 9 and 10 of UP800 and run jumper wires from the traces to pins 9 and 10 of UP800.
  - 0.02mm jumper wire is recommended.
- Ensure that the backlight circuit has its input voltage (VIN) by measuring on BOTH SIDES of FP800, which is the backlight fuse.
  - Voltage on both sides of the fuse should be equivalent to PPBUS_AON.
  - If the backlight fuse is blown, check for a short on backlight output (PPVOUT_LCDBKLT) and on backlight input (PPVIN_LCDBKLT_F).
  - If the fuse is blown without a short, proceed to the "Backlight fuse (FP800) blown in the absence of a short to ground" repair steps below.
- Check that the backlight circuit is being enabled, the screen will need to be connected for the enable signal to be sent out.
  - measure voltage on RP842. BKLT_EN_R / BL_PWR_EN should measure around 1.8v while a GOOD known display is connected.
    - If backlight EN is missing, be sure that you do not have a parts issue with your display or logic board to display cable.
    - BKLT_EN missing on this board due to a board issue is very rare, but may be cause by a failed PMIC (U8100) or failed iGPU in the M1 SoC itself.
- Ensure you have continuity between pin 1 of RP831 (LCDBKLT_FB_XWR) and PPVOUT_LCDBKLT.
  - Although rare on this board, it is worth checking to see if the backlight feedback trace is blown. Without feedback, the backlight driver will not produce its output.
- Check the 5v input to UP800 (PP5v_BKLT_A and PP5v_BKLT_D).
  - RP845 or RP844 may blow if UP800 fails. Ensure you have 5v on both of the above listed lines. If low, replace the blown resistor(s) and UP800.
    - If you have VIN (PPVIN_LCDBKLT_F), Enable (BKLT_EN), and both 5v lines (PP5v_BKLT_A and PP5v_BKLT_D), and no backlight output with the absence of a short to ground, replace the backlight driver (UP800).**

### Repair Steps
#### Backlight output shorted to ground
- Find and replace shorted component [How to find short circuits](How_to_find_short_circuits.md)
  - Ensure the short is not caused by the display. Be sure to measure with and without the display connected.
  - Most commonly, a short on backlight output is caused by a shorted capacitor.

#### Device has backlight output on a known good display, but not on the originally installed display
- Replace the display assembly. Use only a display for a A2337 MacBook Pro. **Earlier Intel MacBook displays will not work.**

#### Backlight fuse (FP800) blown in the absence of a short to ground
- Replace the backlight fuse with a fuse from a donor board or a compatible replacement.
  - 0603 package size, 3 amp, 32v fuse. Brand does not matter.
- Before applying power be sure to double check for a short to ground. Check for a short to ground on backlight output and backlight input.

#### PP5v_BKLT_A or PP5v_BKLT_D absent or low
- Ensure PP5v_S2 is present to both resistors prior to replacing any components
  - If PP5v_BKLT_A is absent or low, replace RP845 and UP800.
  - If PP5v_BKLT_D is absent or low, replace RP844 and UP800.
