---
title: "Nintendo 3DS blue light turns on then turns off"
pageid: 1422
revid: 4807
kind: repair_guide
source: "https://repair.wiki/w/Nintendo_3DS_blue_light_turns_on_then_turns_off"
history: "https://repair.wiki/index.php?title=Nintendo_3DS_blue_light_turns_on_then_turns_off&action=history"
permalink: "https://repair.wiki/index.php?oldid=4807"
last_edited: "2024-09-06T16:48:41Z"
contributors:
  - "SonoSooS"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Nintendo 3DS"
  - "Stubs"
infobox:
  Device: "Nintendo 3DS"
  Affects_parts: "Screen flex cable, Motherboard"
  Type: "Teardown, Part replacement, Cleaning, Software, General"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Nintendo 3DS blue light turns on then turns off

## Problem description
After pressing the Power button, the blue Power LED starts to fade in, but after a second or so it just turns off.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- The 3DS *tries* to turn on when pressing the Power button, but it turns itself off
- There may be an audible pop noise when the blue Power LED turns off
- When turning off, the blue Power LED either fades out gracefully, or it instantly turns off
- The  problem may be intermitten, but it will trigger more often over time

## Solution
The solution vastly depends on whether it's caused by a software problem or a hardware problem.

If the Power LED fades out slowly, then it's almost always a software-related problem.

However, if the Power LED turns off instantly after fading in to blue (especially if accompanied by a loud popping noise), then it's usually a hardware-related fault.

### Diagnostic Steps
- Does the hinge position (open, half-open, closed) influence if the 3DS turns off?
  - If so, it's a damaged flex cable going into the top screen assembly, it's a hardware issue.
- Does the Power LED (blue light) go out instantly? It takes around the same time to gently fade in as it takes to fade out, so the difference is easily distinguishable.
  - If the Power LED fades out gently and slowly, then it's a software problem.
  - If the Power LED turns off instantly, then it's usually a hardware problem.

### Repair Steps
#### Common troubleshooting steps
##### Eject game cartridge
Some unlicensed game cartridges may draw excessive current, or even short out the cartridge pins due to loose tolerances of the cartridge case and missing pin alignment guides.

##### Eject SDCard
In some rare cases, the SDCard may become shorted (especially if it's a microSD), remove it just in case.

#### Software repair steps
##### Check SDCard
If the system is softmodded, the presence of an SDCard with the correct files on it may be necessary for the system to boot.
If the system is *definitely* not softmodded, you may just eject the SDCard, and skip this step.

If the pins of the SDCard are dirty, it may not be recognized by the system.

If an SDCard with the necessary files on it are not found, the softmodded bootloader will signal this error by gracefully shutting the system down.

- Eject the SDCard from the system
- Gently clean the pins, making sure to not scratch up the rest of the SDCard (especially if it's a microSD), and to not bend or remove the pins on it
- Re-insert the SDCard

If none of this helps, the SDCard may be formatted wrong, or important boot files may be missing.

- It **must** be FAT32, and sector size must be between 512 and 32768 (32k) inclusive.
- Depending on the type of softmod, one of these files must be present and valid:
  - /boot.firm (applicable if softmodded with boot9strap ("b9s") or fastboot3DS ("fb3DS"))
  - /arm9loaderhax.bin (applicable if softmodded with arm9loaderhax)

#### Hardware repair steps
The system only shuts down without the Power LED fading out, if something is either shorted, or open.

Causes:
- Top or bottom screen backlight is open
  - Almost always caused by a damaged display flex (top screen) or sometimes by a damaged backlight flex (bottom screen).
- Top or bottom screen backlight is shorted
  - Usually caused by a damaged display, or board damage (display connector, water damage, etc.)
- Top or bottom screen high voltage (+10V, -15V) is shorted
  - Can be caused by a cracked, or otherwise damaged display panel or display flex
- Top ***and*** bottom screen high voltage is open
  - Almost always caused by a damaged display flex or damaged display connector, or just missing / badly plugged in LCD
- Separate power rails shorting together
  - Unknown, usually caused by board damage (water damage?)
- Certain data lines shorting to power lines or GND for an extended period of time
  - Unknown, can be caused by damaged camera flex, but very rarely by damaged display flex.
- One of the speakers are open, or their connections to the CODEC chip are broken
  - Unknown why this causes an emergency shutdown. It shouldn't, yet it does.

Possible diagnosis and repair methods:

- Check top screen assembly flex cables, replace display if display flex or display is broken.
- Check bottom screen backlight cable, replace or repair display if display, display flex, or backlight flex is broken.
- Check display, backlight, and camera flex cable connectors on the motherboard, replace connectors if they are damaged or suspiciously unhealthy-looking.
- Check for water damage, especially near the flex cable connectors and the PMIC area first.
- Check if the speakers and their flex cable are intact and functional. They should make a pop or hissing noise before the system does an emergency shutdown.
