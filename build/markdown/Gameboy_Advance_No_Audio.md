---
title: "Gameboy Advance No Audio"
pageid: 5473
revid: 8706
kind: repair_guide
source: "https://repair.wiki/w/Gameboy_Advance_No_Audio"
history: "https://repair.wiki/index.php?title=Gameboy_Advance_No_Audio&action=history"
permalink: "https://repair.wiki/index.php?oldid=8706"
last_edited: "2025-07-12T21:18:55Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Gameboy Advanced"
  - "Stubs"
infobox:
  Device: "Gameboy Advanced"
  Affects_parts: "Motherboard"
  Needs_equipment: "Soldering iron, microscope, Multimeter"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Gameboy Advance No Audio

## Problem description
The Device produces no audio.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- No Audio on the Speaker
- Audio only works with headphones

### Diagnostic Steps
The first step is to understand if the problem is no audio at all or if it works with headphones, so first try with headphones and see if audio works.

If you get audio with headphones but nothing on speaker the first step is to try a new speaker.

Diagnosing the audio circuit.

The Audio Chip gets 2 signals from the CPU on these resistors R30 and R3 with the device on you should have around 1V on those 2 points.
![Gameboy Advance Audio signals from CPU](images/3/3b/Gameboy_Advance_Audio_signals_from_CPU.png)
The next thing to check is if the Audio Chip is getting the correct voltages to operate.
![Gameboy Advance Audio AMP voltages](images/a/a9/Gameboy_Advance_Audio_AMP_voltages.png)

The next thing to check is if the volume potenciometer is working properly

Place your the red probe of your multimeter on PIN 10 of the Chip and move the volume potencimeter the voltage should change from around 0.5V all the way to 3V.
![Gameboy audio amp pin 10](images/6/60/Gameboy_audio_amp_pin_10.png)
IF audio is only working on Headphones it is possible there is a problem on the audio Jack it is common to have corrosion inside this port.
![Corrosion Gameboy Audio Jack](images/5/54/Corrosion_Gameboy_Audio_Jack.png)

### Repair Steps
If the CPU signal is missing there may be a broken solder joint by the CPU inspect the area under a microscope and you can maybe reflow the pins, there can also be a break in the line in the middle of the PCB.

If 3V is missing from any of the points on the IC you can make a jump to the battery connector since this voltage is generated from the battery.

If the voltage is not working properly on PIN 10 the solution is to replace the potentiometer.

If you have corrosion inside the Audio jack clean it as must as possible and be careful not to damage it since this part is really hard to find.

If the Audio works but its very quiet you can replace the Capacitor behind the audio jack its a 100UF 4V.

If you have a device with ripped pads on the potentiometer the only pads you need to restore are these.
![Ripped pads Gameboy](images/b/bc/Ripped_pads_Gameboy.png)
