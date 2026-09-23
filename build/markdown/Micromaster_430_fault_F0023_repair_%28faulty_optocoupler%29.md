---
title: "Micromaster 430 fault F0023 repair (faulty optocoupler)"
pageid: 1904
revid: 4267
kind: repair_guide
source: "https://repair.wiki/w/Micromaster_430_fault_F0023_repair_(faulty_optocoupler)"
history: "https://repair.wiki/index.php?title=Micromaster_430_fault_F0023_repair_(faulty_optocoupler)&action=history"
permalink: "https://repair.wiki/index.php?oldid=4267"
last_edited: "2024-07-09T11:24:20Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Micro Master 430 6SE6430-2UD31-5CA0"
infobox:
  Device: "Micro Master 430 6SE6430-2UD31-5CA0"
  Affects_parts: "HCNW3120, 330Ohm, 2.7kOhm"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Micromaster 430 fault F0023 repair (faulty optocoupler)

## Problem description
Diagnosing and fixing error/fault code F0023 on Siemens micromaster 430 inverter/VFD. This particular guide concerns a faulty driving optocoupler.
![Faulty phase (middle) showcase with lightbulbs (Figure 1)](images/5/5a/20240626_135216.jpg)
![Correctly functioning gate signal (Figure 2)](images/f/fb/20240626_152924.jpg)
![Faulty gate signal (Figure 3)](images/b/bf/20240626_152937.jpg)
![Faulty components (Figure 4)](images/1/1a/20240626_151436.jpg)

## Symptoms
- Fault F0023 over 20Hz output frequency, "working" under 20Hz but choppy motor movement.
- When starting the motor on low frequency (below 10Hz), it spins, stops, then spins again

## Solution
First, check if the IGBT module itself is functioning and not faulty, use an LCR meter and measure all 6 output gates against their respective emitters. If the IGBT is fine, measure the signal going to it while running, BE VERY CAREFUL! IF YOU SHORT SOMETHING WHILE MEASURING THE GATES WHEN THE INVERTER IS RUNNING IT COULD EXPLODE!. I recommend soldering thin enameled wires from the gates and emitters for ease of measurement. In this case, one of the gates was not being driven properly, (figures 2,3). Tracked where the driving signal is coming from, it was from the right most opto coupler. The output side was fine (every component measured correctly, resistors and the SOT23 diodes) but after measuring the input side (figure 4), both resistors (330 and 2.7k) were different values. Although even when replaced, the inverter still acted weird. Turns out, even though the optocoupler diode measured fine (1.4v drop on pin 2-3) the output side was faulty. Replacing the optocoupler fixed this issue.
