---
title: "Raspberry Pi Faulty PAM2306 Repair"
pageid: 971
revid: 2348
kind: repair_guide
source: "https://repair.wiki/w/Raspberry_Pi_Faulty_PAM2306_Repair"
history: "https://repair.wiki/index.php?title=Raspberry_Pi_Faulty_PAM2306_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=2348"
last_edited: "2024-01-13T22:27:34Z"
contributors:
  - "ASRepairs"
  - "HaileyKitty"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Raspberry Pi"
  - "Stubs"
infobox:
  Device: "Raspberry Pi"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Raspberry Pi Faulty PAM2306 Repair

## Problem description
The PAM2306 is a dual step-down DC/DC converter that is used in the following [Raspberry Pi](Raspberry_Pi.md) models:

- Raspberry Pi **1** (A+ and B+)
- Raspberry Pi **2** (all)
- Raspberry Pi **3** (model B only)
- Raspberry Pi **Zero** (all)

![PAM2306](images/4/4f/300px-PAM2306.jpg)

## Symptoms
Possible symptoms of a faulty PAM2306 include:

- System doesn't turn on or crashes immediately after turning on.
- System runs fine for 10 minutes, then turns off and won't turn on again for some time.
- Red PWR LED flickers or turns off completely (if present)
- 5V present at GPIO 2, but no 3.3V on GPIO 1

## Solution
The PAM2306 drives both the 3.3V and the 1.8V power rails of the [Raspberry Pi](Raspberry_Pi.md) by producing two PWM (square wave) signals which are fed through coils connected to pins 8 and 2.

Usually, the generated square waves have a frequency of around 1.8MHz.

If a short circuit is detected, the frequency is reduced to around 600kHz, and shorter pulses are generated.
![The PWM signal on Pin 8 of a PWM2306 during normal operation](images/3/37/600px-PAM2306_PWM_ok.png)
![Signal on Pin 8 of a PWM2306 in short circuit protection mode](images/2/21/600px-PAM2306_current_limiting.png)
[[File:1200px-PAM2306 implementation schematic.png|alt=The PAM2306 chip in the schematic of the Raspberry Pi 2[2]|thumb|The PAM2306 chip in the schematic of the Raspberry Pi 2]]

### Diagnostic Steps
![The relevant contacts on a Raspberry Pi 2](images/c/cd/450px-PAM2306_Raspberry_Pi_2_v1.1.jpg)
![The relevant contacts on a Raspberry Pi Zero](images/d/db/450px-PAM2306_Raspberry_Pi_Zero.jpg)

To find the exact fault, the following tests can be performed:

#### Supply voltage
To function properly, the chip needs a voltage of 5V on pins 1, 6 and 7. All those pins are directly connected to the Raspberry Pi's 5V rail, so testing for 5V on GPIO 2 will do.

If the voltage on GPIO 2 is close to 0V, the chip is most likely not the problem. Usually, the big diode near the micro-USB port needs to be replaced instead.

#### Coils
Remove all power from the Raspberry Pi and measure the resistance between the two sides of each coil (marked by orange and yellow arrows in the images). Measuring the coils directly can be tricky on some PCBs. Sometimes measuring between the PAM2306 and one of the brown capacitors is a better option.

If a coil is okay, the resistance should be a few Ohms at most.

#### Short circuits
Remove all power from the Raspberry Pi and measure the resistance between the voltage outputs (orange arrows) and the metal casing of the micro-USB port. There should be a resistance of many kOhms.

If there is a short circuit, the chip is most likely not the problem. Try locating the short circuit (see [Detecting short circuits](Short_Circuits_-_Repair_Basics.md)).

#### Analyzing the PWM signals
If an oscilloscope is available, the voltages at the PWM outputs of the chip can be analyzed directly (the two PWM outputs are marked with yellow arrows in the pictures).

- If there is no signal, but only a constant voltage on one of the PWM outputs, the chip is broken.
- If there is a 600kHz signal on one of the PWM outputs, and there is no short circuit, the chip is broken.
- If there is a 1.8MHz signal on both PWM outputs, the chip working fine.
![A 1.8MHz square wave is measured. There is quite a bit of noise in the measured signal because the GND probe has a bad connection.](images/7/7a/Bad_probing.png)
Depending on your probing technique, the measured signal may look quite a bit less clean than the square wave in the image above. This usually doesn't mean the PAM2306 is faulty, as long as the frequency is correct.

### Repair Steps
Replacing the chip

If no other fault could be found in the above steps, the chip needs to be replaced.

Replacing the chip is only possible with hot air. Using a soldering iron is not possible because the chip has a soldered ground pad in its middle.

The cheapest and easiest way to get a replacement chip is to buy a Raspberry Pi Zero, or to take a chip from another broken Raspberry Pi.

Make sure to thoroughly check for shorts after replacing the chip **(don't forget to check for shorts between the 1.8V and 5V rails as well as between the 3.3V and 5V rails!!)**.

## References
1. [↑](PAM2306_%28Raspberry_Pi%29.md) *[https://www.diodes.com/assets/Datasheets/PAM2306.pdf PAM2306 datasheet]*, Diodes Incorporated, May 2021
1. [↑](PAM2306_%28Raspberry_Pi%29.md) *[https://datasheets.raspberrypi.org/rpi2/raspberry-pi-2-b-reduced-schematics.pdf Raspberry Pi 2 Model B schematic]*, Raspberry Pi Foundation, November 16, 2016
