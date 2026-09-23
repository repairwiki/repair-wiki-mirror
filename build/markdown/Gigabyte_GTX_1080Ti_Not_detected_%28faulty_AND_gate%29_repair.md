---
title: "Gigabyte GTX 1080Ti Not detected (faulty AND gate) repair"
pageid: 1636
revid: 3586
kind: repair_guide
source: "https://repair.wiki/w/Gigabyte_GTX_1080Ti_Not_detected_(faulty_AND_gate)_repair"
history: "https://repair.wiki/index.php?title=Gigabyte_GTX_1080Ti_Not_detected_(faulty_AND_gate)_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3586"
last_edited: "2024-03-05T17:36:04Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for GTX 1080"
  - "Repair guides for GTX 1080Ti"
infobox:
  Device: "GTX 1080Ti, GTX 1080"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Gigabyte GTX 1080Ti Not detected (faulty AND gate) repair

## Problem description
Fixing an issue with the Gigabyte GTX 1080Ti Turbo or Gaming OC (they use the same PCB) not being detected while the fans are spinning. This problem makes the GPU invisible to the rest of the system meaning not detected anywhere (MATS, Windows). And if you have a post card, you'll notice the motherboard zooms past B2 (state where the card would be detected) indicating the PC is not even trying to communicate with the card. For this repair, it is recommended to use a mining riser to make measuring easier.

This specific problem is related to the PCIE detection circuit, specifically, the PEX_RST AND gate.
![Location of the PEX_RST AND gate on the Gigabyte 1080Ti (Figure 1)](images/9/9c/Gigabyte_1080Ti_location_of_AND_gate.jpg)
![AND gate up close with measurements (Figure 2)](images/b/be/20240305_182709.jpg)

## Symptoms
- Not detected with fan spin.
- BIOS not being read, pins 2 and 5 silent when measured with an oscilloscope.
- All voltages present and core heating up normally.
- Vcore voltage stuck at 0.8V, not dropping to 0.7V to indicate an initialized core.

## Solution
### Diagnostic Steps
- Start by disassembling the card.
- Make sure there are no [shorts](Short_Circuits_-_Repair_Basics.md) on any voltage rail, follow [this guide](Nvidia_Pascal_GPU_Diagnosing_Guide.md) if you're unsure how.
- Power the card on with the riser **with the data cable plugged in,** this is important!
- Measure pins 1, 2, 4, and 5 on the AND gate (Figure 2) with your multimeter on voltage mode. Be careful when measuring as to not short anything!
  - The "correct" measurement should yield 3.3, 3.3, 1.8, and 1.8V respectively.
  - If you measure the correct values, you have a different issue! check the diagnosis guide or other guides on the wiki.
- If this is your issue, pin 4 should be reading close to 0V. Which indicates a faulty PEX_RST AND gate.

### Repair Steps
- Take off the faulty AND gate.
- Replace with a suitable AND gate.
- You should now measure 1.8V on the output (pin 4) of the gate.
- Put the card back together and test!

On this card, the original was a "[https://www.ti.com/lit/ds/symlink/sn74lvc1g08.pdf?ts=1709638903001&ref_url=https%253A%252F%252Fwww.ti.com%252Fproduct%252FSN74LVC1G08%252Fpart-details%252FSN74LVC1G08DBVRG4 SN74LVC1G08]" with "CEF" marking, I have replaced it with a "[https://assets.nexperia.com/documents/data-sheet/74LVC1G08.pdf 74LVC1G08]" that has the marking "VE". Use Mouser or equivalent to buy the new part or take it from another donor.
