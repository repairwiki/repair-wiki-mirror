---
title: "Zotac GTX 1080Ti Not turning on, not detected (short on PEX) repair"
pageid: 1641
revid: 3595
kind: repair_guide
source: "https://repair.wiki/w/Zotac_GTX_1080Ti_Not_turning_on,_not_detected_(short_on_PEX)_repair"
history: "https://repair.wiki/index.php?title=Zotac_GTX_1080Ti_Not_turning_on,_not_detected_(short_on_PEX)_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3595"
last_edited: "2024-03-07T15:43:13Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for GTX 1080Ti"
  - "Stubs"
infobox:
  Device: "GTX 1080Ti"
  Affects_parts: "GPU Core"
  Needs_equipment: "multimeter, soldering iron, soldering station, BGA station, thermal camera"
  Type: "BGA, Soldering"
  Difficulty: "4. Specialist"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Zotac GTX 1080Ti Not turning on, not detected (short on PEX) repair

## Problem description
Solving an issue with a Zotac GTX 1080Ti that does not get detected and shows no picture.
This particular problem is characterized by having sub 5 Ohms on the PEX rail (Figure 1)
![Location of PEX rail on a Zotac GTX 1080Ti (Figure 1)](images/0/0a/Location_of_PEX_rail_on_a_Zotac_GTX_1080Ti_(Figure_1).jpg)
![PEX rail under the microscope on a Zotac GTX 1080Ti (Figure 2)[[File:Dead 1080ti core.jpg|thumb|173x173px|Source of the short on the card, the core (Figure 3)\]\][[File:Zotac 1080Ti after removing the core (Figure 3).jpg|thumb|182x182px|Zotac 1080Ti after removing the core (Figure 4)\]\]](images/5/51/PEX_rail_under_the_microscope_on_a_Zotac_GTX_1080Ti.jpg)

## Symptoms
- Not detected, not turning on.
- GPU getting hot.
- Sub 5 Ohms measured on PEX rail.
- All voltage rails are present except PEX.

## Solution
### Diagnostic Steps
First, read [this guide](Nvidia_Pascal_GPU_Diagnosing_Guide.md) if you're unsure how to start measuring.

After confirming the symptoms and having measured sub 5 ohms on the PEX rail, you can start by identifying what exactly is [shorted](Short_Circuits_-_Repair_Basics.md). You'll need a lab bench power supply with 10A (recommended) and inject 1V to the rail. If you want to know which side of the inductor is shorted (core side or controller side) just inject to both sides and the shorted side will pull more current. This case, the core side was pulling more current.

After injecting voltage, you'll need to use a thermal camera to detect what is getting hot. This kind of short is hard to detect with IPA or other methods because if the core or a capacitor is shorted, they spread the heat immediately to the surrounding area. In this case, the core itself was the culprit. The heating manifests in the middle lower edge of the core (Figure 3).

At this point, it might not be reasonable to fix this card if you do not already have a spare core and a BGA rework station. This guide will not go into detail about BGA rework and assumes you know how to do it, otherwise, do not attempt to replace the core if this is your first time!

If the source of your short turns out to be a capacitor then just remove it. No need to replace it
### Repair Steps
If the source of the short is the core, start by removing it. After which, confirm that the short is gone after the card has cooled down. If that's the case, simply replace the core.

If the source of your short turns out to be a capacitor then just remove it. No need to replace it.
