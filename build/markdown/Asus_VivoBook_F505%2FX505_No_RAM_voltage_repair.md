---
title: "Asus VivoBook F505/X505 No RAM voltage repair"
pageid: 559
revid: 2073
kind: repair_guide
source: "https://repair.wiki/w/Asus_VivoBook_F505/X505_No_RAM_voltage_repair"
history: "https://repair.wiki/index.php?title=Asus_VivoBook_F505/X505_No_RAM_voltage_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=2073"
last_edited: "2024-01-12T23:20:41Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for VivoBook F505/X505"
infobox:
  Device: "VivoBook F505/X505"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Asus VivoBook F505/X505 No RAM voltage repair

## Problem description
The machine is equiped with X505ZA 2.0 motherboard.

The same board may be used in other VivoBook models. Found missing CPU core voltage.

All previous required voltages OK, but missing RAM voltage; 1.2V not present at corresponding power coil.
![X505ZA 2.1 (Figure 1)](images/6/66/X505ZA_2.1.jpg)

## Symptoms
- No RAM voltage (Figure 1)
![X505ZA 3.1 (Figure 2)](images/3/37/X505ZA_3.1.jpg)
![X505ZA 1.1 (Figure 3)](images/c/cb/X505ZA_1.1.jpg)

## Solution
Inspecting opposite side of the board, corroded resistor with broken trace found. Result to be TON line of RAM voltage controller (Figure 2).

No schematic, nor boardview available for this motherboard (at the moment). As usual value fort such resistor is in range of 180-620K, I choosed 560K. (Figure 3). Using 0603 size helped me to bypass broken trace also.

Once correct RAM voltage appeared, CPU core voltage comes on too. Motherboard came back to life.
