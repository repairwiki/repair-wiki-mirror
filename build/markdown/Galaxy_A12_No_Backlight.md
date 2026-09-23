---
title: "Galaxy A12 No Backlight"
pageid: 4772
revid: 7859
kind: other
source: "https://repair.wiki/w/Galaxy_A12_No_Backlight"
history: "https://repair.wiki/index.php?title=Galaxy_A12_No_Backlight&action=history"
permalink: "https://repair.wiki/index.php?oldid=7859"
last_edited: "2025-06-21T21:09:55Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Galaxy A12"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Galaxy A12 No Backlight

## Problem description
The Device turns on but screen is very dim and you need to point a flashlight to see something.
![Galaxy A12 With No Backlight](images/f/f4/Galaxy_A12_No_Backlight.jpg)

## Symptoms
- The Phone Turns on but Backlight is not working

### Diagnostic Steps
The first step is to try to swap parts before assuming there is a problem with the motherboard, so start by trying a new display.

If a new display does not fix the issue inspect the main FPC on the board it is common to brake on A series, but usually a bad FPC will also cause other issues to the Phone.

If there is no damage to the FPC we will have to diagnose the backlight circuit, this circuit on the CPU side of the motherboard.

Every component inside the red line on the image bellow is part of the Backlight circuit.
![Galaxy A12 Backlight Circuit Location](images/4/48/Galaxy_A12_backlight_circuit_location.png)
The first thing you wanna check is this coil, this coil in on the output of the circuit and it is common to leak "oil" this usually means that there is a short circuit on this line.
![Galaxy A12 Backlight Coil Leaking](images/1/15/Galaxy_A12_Backlight_Coil_Leaking.png)

With your multimeter in Diode Mode you wanna check these components for shorts bellow is and image with the expect values of a good phone.
![Galaxy A12 Backlight Circuit Diode Values](images/d/dd/Galaxy_A12_Backlight_Circuit_Diode_Values.png)

The most common issue is for one of these caps to blow up and short the circuit.
![Galaxy A12 Backlight coil shorted](images/d/d8/Galaxy_A12_Backlight_coil_shorted_.png)

### Repair Steps
If there is any physical damage to the main FPC the repair is quite straight forward all it's needed is to replace it.

If you have a shorted Capacitor you can replace it from one taken of a donor phone, you will also need to replace the leaking coil.

There are cases where you have to rebuild part of the Backlight Circuit since a short on these lines often kills the Backlight Controller IC.

There are "Kits" on websites like aliexpress that include everything you need to replace, 2 big Capacitors, Backlight Controller, Output Coil, Diode.

When replacing any component around this area be careful to not use excessive heat since the CPU is close by.

Replacing any component on this motherboard is not hard and doesn't take much heat since the board is quite small and thin.
