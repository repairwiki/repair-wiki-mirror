---
title: "Adam Audio Sub 7 not turning on, or shuts down when signal present"
pageid: 3655
revid: 6466
kind: repair_guide
source: "https://repair.wiki/w/Adam_Audio_Sub_7_not_turning_on,_or_shuts_down_when_signal_present"
history: "https://repair.wiki/index.php?title=Adam_Audio_Sub_7_not_turning_on,_or_shuts_down_when_signal_present&action=history"
permalink: "https://repair.wiki/index.php?oldid=6466"
last_edited: "2025-05-08T01:20:14Z"
contributors:
  - "Juanmartinvk"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Adam Audio Sub 7"
  - "Stubs"
infobox:
  Device: "Adam Audio Sub 7"
  Affects_parts: "Power supply"
  Needs_equipment: "Screwdrivers, multimeter, soldering iron, hot air station, desoldering pump"
  Type: "Soldering, Teardown, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Adam Audio Sub 7 not turning on, or shuts down when signal present

## Problem description
If your Adam Audio Sub 7 does not turn on, or powers off when you slightly increase the volume, the issue is likely a fault in the internal switch-mode power supply (Figure 1, left).

### ⚠️ Safety Warning
Switch-mode power supplies contain dangerous high voltages, even when unplugged. Components like capacitors can hold a charge that may be lethal. Only attempt this repair if you are familiar with high-voltage electronics and the appropiate safety precautions.![Power supply (left), amplifier board (right)](images/0/05/Adam_Audio_Sub_7_amplifier_panel.jpg)

## Solution
Identify and test the following suspect components in the power supply:

- **D6 and D8**: These secondary output dual Schottky diodes are the prime suspects. They've blown in all the units I've repaired. Check for shorts with a multimeter. Model number is F12C20C. I've not been able to find this exact part, but a suitable replacement with even better specs is the STPS20200CFP from ST, which is available at Mouser and Digikey.
- **D5 and D9**: One or both of these diodes from the primary Snubber network might be blown. Check with multimeter in diode mode for shorts or open circuit. Note that these may be covered in black gunk. D5 is FR107 and D9 is 1.5KE200A.
- **R4**: This 15Ω SMD resistor is in series with the auxiliary winding of the transformer, which provides power to the main switching IC. This one tends to fail open (check with multimeter). This in turn causes the PSU to turn on, but then to fail when presented with a very mild load, as the switching chip can't get enough current from the primary dropper resistor (R19).
- **U5**: This is the main switching chip, model KA5Q1565RF. I've had to replace this chip only once, and it was very evidently burnt and showed cracks in the package.
