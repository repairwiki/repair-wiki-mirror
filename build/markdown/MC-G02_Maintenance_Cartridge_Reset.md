---
title: "MC-G02 Maintenance Cartridge Reset"
pageid: 3958
revid: 6866
kind: repair_guide
source: "https://repair.wiki/w/MC-G02_Maintenance_Cartridge_Reset"
history: "https://repair.wiki/index.php?title=MC-G02_Maintenance_Cartridge_Reset&action=history"
permalink: "https://repair.wiki/index.php?oldid=6866"
last_edited: "2025-05-16T22:55:28Z"
contributors:
  - "Antcz"
anonymous_edits: 0
categories:
  - "Missing device page"
  - "Repair guide"
  - "Repair guides for MC-G02"
infobox:
  Device: "MC-G02"
  Affects_parts: "QM8-0042"
  Needs_equipment: "Arduino Uno, Soldering Station"
  Type: ""
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MC-G02 Maintenance Cartridge Reset

## Problem description
The Canon MC-G02 is a disposable maintenance cartridge, however you can read the chip inside it and write it back with an Arduino sketch to reset the counter.
## Symptoms
- When you do a printer head cleaning or try to print, a message will appear telling you that the maintenance cartridge is full.
- The same message can be displayed on the small printer screen.

## Solution
- Make sure you have an Arduino and a soldering station.
- Download Arduino IDE and Visual Studio Code.
- Connect the QM800-0042 board to the Arduino:
  - VCC ---> VCC
  - SCL ---> SCL (pulled up by a 10k resistor to VCC)
  - SDA ---> SDA (pulled up by a 10k resistor to VCC)
  - GND ---> GND
- Download the Arduino sketch from https://github.com/wangyu-/canon_mc-g02_resetter
- Connect the Arduino.
  - Open "sketch_hack_read.ino"
  - Tools > Board (select your Arduino Board)
  - Tools > Port (select the detected port)
  - Upload to your Arduino.
- Once it's successfully uploaded, close the Arduino IDE.
- Open Visual Studio Code and go to Extensions; download the Serial Monitor extension.
  - Go Terminal > New Terminal
  - The Terminal window will open, go to the SERIAL MONITOR tab.
  - Connect the Arduino board and click Start Monitoring
  - Copy the dump to a text file on Visual Studio Code and remove all the spaces between the code.
- Open "sketch_hack_write.ino"
  - Insert the dump you just read from Visual Studio Code.
  - SAVE (very important, once you have this sketch with your dump, you skip a lot of steps)
  - Upload
  - Done, the chip has been reset.

Note: Once your Arduino has the code uploaded, you only have to solder the pins and connect to USB to reset it. If the code has been wiped from the Arduino you can just upload it with the "sketch_hack_write.ino" with your dump.

## **Gallery**
![MC-G02.JPEG](images/4/4d/MC-G02.JPEG)
![QM8-0042 Back.JPEG](images/8/8d/QM8-0042_Back.JPEG)
![QM8-0042 Pinout.png](images/6/66/QM8-0042_Pinout.png)
![QM8-0042 with Resistors.JPEG](images/4/4b/QM8-0042_with_Resistors.JPEG)
![QM8-0042 Soldered Wires with Resistors.JPEG](images/7/75/QM8-0042_Soldered_Wires_with_Resistors.JPEG)
![QM8-0042 Programming.JPEG](images/a/ac/QM8-0042_Programming.JPEG)
![VSC Paste Rom.png](images/8/88/VSC_Paste_Rom.png)
![Wiring Diagram.png](images/d/d4/Wiring_Diagram.png)
