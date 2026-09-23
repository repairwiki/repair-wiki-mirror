---
title: "Nvidia Pascal (GTX 1000) GPU Diagnosing Guide"
pageid: 378
revid: 4914
kind: explanatory_guide
source: "https://repair.wiki/w/Nvidia_Pascal_(GTX_1000)_GPU_Diagnosing_Guide"
history: "https://repair.wiki/index.php?title=Nvidia_Pascal_(GTX_1000)_GPU_Diagnosing_Guide&action=history"
permalink: "https://repair.wiki/index.php?oldid=4914"
last_edited: "2024-09-21T23:24:46Z"
contributors:
  - "ASRepairs"
  - "Galkinvv"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for GTX 1060"
  - "Explanatory guides for GTX 1070"
  - "Explanatory guides for GTX 1070Ti"
  - "Explanatory guides for GTX 1080"
  - "Explanatory guides for GTX 1080Ti"
infobox:
  Device: "GTX 1060, GTX 1070, GTX 1070Ti, GTX 1080, GTX 1080Ti"
  Type: "Troubleshooting/Diagnostics"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Nvidia Pascal (GTX 1000) GPU Diagnosing Guide

    - Note: This guide applies to most Pascal-based graphics cards, ranging from the GTX 1060 to the 1080 Ti. While some vendors may use different PCBs or components, the general operational principles remain the same unless specified. For the purpose of this guide, we will be using a reference GTX 1080 as an example.***

- Have any questions? Need help with a specific GPU problem? Post to [https://www.reddit.com/r/GPURepair/ /r/GPURepair]!*

## The Card Layout
[[File:GTX 1080.jpg|none|thumb|600x600px|GTX 1080 Reference board (Figure 1) **PCB Image courtesy of [https://www.techpowerup.com/review/nvidia-geforce-gtx-1080/ TechPowerUp]**]]

Before proceeding, it's crucial to visually inspect the card for physical damage, particularly cards without a backplate, which can be more vulnerable to component loss due to mishandling.

Once you've confirmed there's no physical damage to the card, you can proceed with using a multimeter to check the resistances of the voltage rails.

## Step 1: Base Voltage Rails (12V, 3.3V)
Base voltages are supplied to the card through the motherboard and external 8-pin power connector(s). Here is a page with further details: [What are the Base Voltage rails for GPUs?](Base_Voltage_Rails_For_GPUs.md)

### 12V rails
The card receives 12V power through the PCIe slot and additional 6-8-pin connectors. Start by measuring the resistances of the 12V rail coming from the PCIe slot (first 3 pins, see Figure 1).

Next, measure the resistance of each inductor for external power connectors (some cards have multiple external power connectors, and each of them has its inductor).

The resistance values can vary among different cards, but they should generally be in the thousands of ohms or higher. A resistance reading of 50 ohms or less indicates a [short circuit](Repair_Basics_-_Short_Circuits.md) on the card causing the computer not to power on due to overcurrent protection (OCP) by the power supply.

Solution: Check out this page dedicated to [Base Voltage Rail Short on Pascal GPUs](Short_on_base_voltage_rail_on_Pascal_GPUs_repair.md).

### 3.3V rail
The card receives 3.3V power exclusively from the PCIe slot. You can find the pins in the front (4th pin going left from the PCIe key notch) and on the back (2nd and 3rd pins going from the notch again).

If you measure less than 50 ohms on one or more base rails, it signifies a short circuit on the card, potentially causing the computer not to power on due to overcurrent protection (OCP) by the power supply.

Solution: Check out this page dedicated to [Base Voltage Rail Short on Pascal GPUs](Short_on_base_voltage_rail_on_Pascal_GPUs_repair.md).

If no shorts are measured, you can proceed with troubleshooting.

## Step 2: Minor Voltage rails. (5V, 1.8V, VCore, VMem, and PEX)
Minor voltage rails are created by the card itself using the base rails through either [Linear Voltage Regulators](wikipedia%3ALinear_regulator.md) or [Step-Down Buck Converters.](wikipedia%3ABuck_converter.md)

Check the resistance of the output of these minor rails and compare them with Figure 1.

The VCore rail often has very low resistance on 1000+ series cards, making it unhelpful to measure its resistance directly. Instead, measure its resistance against the 12V rails (not GND).

If you identify lower resistance on any of these rails, refer to their respective pages linked below. Otherwise, continue with the guide.

## Step 3: Powering on the card
Assuming there are no shorts detected, you can proceed by plugging the card into the motherboard and initiating testing. Alternatively, you can use a Lab Bench Power Supply and a riser. This way, you're not risking damaging the motherboard and it enables you to move the card around more easily and read the current draw of the card.

Switch your multimeter to DC Voltage mode and start by measuring the base rails first. If they are present, continue to the minor rails. Minor rails activate in series; if one doesn't start, the subsequent ones in the series will also remain inactive.

### Power sequence
Power Sequence: The typical order in which these rails activate in most Pascal GPUs is: **5V → 1.8V → VCore → VMem/PEX.** If one of these rails is missing, refer to their respective troubleshooting pages:

- [5V Rail on Pascal GPUs.](5V_Rail_on_Pascal_GPUs_Explained.md)
- [1.8V Rail on Pascal GPUs.](1.8V_Rail_on_Pascal_GPUs_Explained.md)
- [Vcore Rail on Pascal GPUs.](VCore_Rail_on_Pascal_GPUs_Explained.md)
- [Vmem Rail on Pascal GPUs.](VMem_Rail_on_Pascal_GPUs_Explained.md)
- [PEX Rail on Pascal GPUs.](PEX_Rail_on_Pascal_GPUs_Explained.md)

## Step 4: No Video Out
If all rails are present, but there's still no video output, one of these factors may be at play: faulty memory, BIOS issues, GPU chip problems, or in some cases, strap-related issues.

### Memory problems
If you've reached this stage, memory issues are the most likely cause. You can confirm this by powering on the card and connecting it to a monitor. If the monitor's backlight turns on without displaying an image after a minute or so, it indicates a memory problem. Refer to the [Nvidia Memory Testing Guide](Nvidia_GPU_Memory_Testing_Guide.md) for further guidance on detecting faulty memory chips.

### BIOS problems
If the memory is functioning correctly, or the card is not detected in MODS testing, the issue may be related to the BIOS. Check the [BIOS Problems on Pascal GPUs](BIOS_Problems_on_Pascal_GPUs_Repair.md) page for troubleshooting steps.

### Straps
![GTX 1080 Straps location on the board. (Figure 2)](images/7/7e/Straps_location_1080.jpg)
![Schematic view of 1080 straps (Figure 3)](images/3/3e/Straps_schematic_gtx_1080.jpg)
Straps can be understood as physical settings for the card. Depending on which series of strap resistors are populated, they instruct the card on various configuration parameters. For example, they can indicate whether the installed memory is from Samsung or Micron.

Assuming there's no physical damage to the strap resistors, check their resistance values outside the circuit. Sometimes, although rarely, these values may change. Refer to the strap locations (Figure 2) and their schematic (Figure 3).
### Crystal Oscillator
Crystal oscillators, often marked with "Y" followed by a number, can occasionally fail, preventing the card from booting up. The frequency of the oscillator in most Pascal GPUs is 27MHz. To test it, you'll need an oscilloscope or a multimeter with an Hz function capable of measuring above 27MHz.
![Location of the crystal oscillator on a reference GTX 1080 (Figure 4)](images/5/54/Pascal_crystal_oscillator_.jpg)

### Dead PCIE data lanes
If the card has been used for mining, there is a chance that the miner has inserted the riser backwards which can fry the first PCIE data lane inside the core. [https://youtu.be/nMs4xI4PWKQ This video explains it more with a potential fix.]

### Dead Core
If everything else is working as they should but still no video out then unfortunately you have a faulty GPU core. Best use for that card is as spare parts since getting hold of a GPU chip by itself is very hard and expensive and replacing it is a very advanced procedure that requires a BGA rework station and it's out of reach for many people.

### Faulty PEX_RST AND gate
The last pin on the front of the PCI-E slot before the notch is a reset signal from the computer to the card, this signal (depending on the manufacturer) sometimes passes straight to the GPU and sometimes through a logical AND gate IC. Those have 5 legs and usually come in the SOT-353 package. Pins 1-2 are the inputs, 3 is GND, 4 is output, 5 is VCC. Pin 4 mostly goes directly to the core and it should be HIGH. If you measure it to be low then measure the inputs/VCC for the gate. If VCC and the inputs are all present then the gate needs to be replaced. [Relevant repair guide](Gigabyte_GTX_1080Ti_Not_detected_%28faulty_AND_gate%29_repair.md).

## Step 5: GPU outputs a picture
Perhaps the card does output a picture but it is not working properly, here are the common problems and their potential fixes.

### Artifacting
Artifacting is most often caused by memory problems, check [Nvidia Memory Testing Guide](Nvidia_GPU_Memory_Testing_Guide.md)

if you do not get memory errors even after 100+MB test in MATS then the core is very likely to be the issue.

### Crashing under load
Just like artifacting, crashing under load is commonly caused by memory or core. However, in rare cases it might be a faulty [MOSFET](Transistors_-_Repair_Basics.md)/PowerStage or the driver/controller for them. In no load scenario, not all Vcore phases are running, only 1-2 are switching. As soon as a higher load appears and the card starts to draw more power, the rest of the phases will start switching, it could be that at this moment the mosfet is faulty that it does not switch properly or the controller is not providing the switching signal.

To diagnose this, you'll need an oscilloscope and measure the gates of every MOSFET. Ensuring the PWM signal on each is as it should.

### Error 43
just like artifacting, error 43 can be caused by faulty memory or core but also BIOS and straps.

Start by making sure the memory is fine as shown in the guide above, then check if the BIOS is not corrupted/modded (flash original bios from either TPU library or manufacturer's site) and check the bios circuit as shown here: [BIOS Problems with pascal GPUs](BIOS_Problems_on_Pascal_GPUs_Repair.md)

After that if the problem persists, check the strap resistors, they can either get knocked off or change in value which will trigger error 43.

If everything is fine but the error persists then the core itself is damaged.
