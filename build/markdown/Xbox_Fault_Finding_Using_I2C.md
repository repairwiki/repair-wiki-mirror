---
title: "Xbox Fault Finding Using I2C"
pageid: 5335
revid: 8553
kind: explanatory_guide
source: "https://repair.wiki/w/Xbox_Fault_Finding_Using_I2C"
history: "https://repair.wiki/index.php?title=Xbox_Fault_Finding_Using_I2C&action=history"
permalink: "https://repair.wiki/index.php?oldid=8553"
last_edited: "2025-07-06T21:41:13Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for Xbox One S"
  - "Explanatory guides for Xbox One X"
  - "Explanatory guides for Xbox Series S"
  - "Explanatory guides for Xbox Series X"
  - "Stubs"
infobox:
  Device: "Xbox One S, Xbox One X, Xbox Series S, Xbox Series X"
  Type: "Troubleshooting/Diagnostics"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Xbox Fault Finding Using I2C

## Problem description
The SouthBridge when detecting a problem with a component on the motherboard creates a Error Log.

Using I2C protocol to communicate with the console we can see the error code the console gives.

These errors can then help us identifying what's wrong with the console.

![Raspberry Pi Pico](images/c/c3/Raspberry_pi_pico.jpg)

## Required tools
In order to connect to the Xbox you will need a Raspberry Pi Pico.

You will also need some wires.

You need a Soldering Iron.
## Preparing the Raspberry Pi
The first step is to flash a custom firmware on the Raspberry Pi.

The best option to do this is to follow the oficial guide on Github [https://github.com/xboxoneresearch/PicoDurangoPOST]

### Connecting the USB-TTL to the console
After flashing the firmware on the Raspberry Pi we are ready to solder 3 points from the motherboard to the raspberry.

Follow the image below the image below.
![Xbox I2C Connection points](images/e/e3/Xbox_I2C_Connection_points.png)

### Connecting the console to the PC
In order to pull the errors from the console we will need a program to communicate with the console, in this guide we will use XboxPostcodeMonitor [https://github.com/xboxoneresearch/XboxPostcodeMonitor?tab=readme-ov-file]

Download and install the software above.

Connect your Raspberry device to the computer, plug in the power supply of to the console and plug it in but dont turn the console on.

Next open the program and select the COM port where your Raspberry is connected to.

Next select your xbox model the click on "Connect"

After that turn the console on

You should get an output like this:
![Xbox Error Example Output](images/f/f6/Xbox_Error_Example_Output.png)

### What to do with the Codes?
The most up to date database of syscon errors is on Xbox POST Error Codes [https://errors.xboxresearch.com/]
