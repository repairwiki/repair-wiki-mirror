---
title: "MacBook Pro A2338 camera not detected after history of liquid damage repair"
pageid: 59
revid: 536
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A2338_camera_not_detected_after_history_of_liquid_damage_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A2338_camera_not_detected_after_history_of_liquid_damage_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=536"
last_edited: "2023-10-29T15:29:41Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A2338"
  - "Stubs"
infobox:
  Device: "MacBook Pro A2338"
  Affects_parts: "Motherboard, Camera, Display assembly"
  Type: "Soldering, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A2338 camera not detected after history of liquid damage repair

## Problem description
No camera detected after a history of liquid damage on the 820-02020 logic board.

## Symptoms
- Camera not detected.
- Possible signs of liquid damage.

## Solution
### Diagnostic Steps
![(Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)

#### Corroded TCON connector with corresponding short on the display (LP610 will also be blown)
- Check continuity on LP670.

1. Place your multimeter in continuity mode and measure across the component. LP610 is a filter, so it is essentially a wire. Your reading should be close to 0.01. You will often find this component visually exploded/burned with adjacent trace damage. Usually, there will also be corrosion on the display camera connector which will require replacement of the connector and sometimes the entire display assembly (left side of the primary display connector). If LP610 measures normally, proceed to the next steps. If LP610 is blown or burned, proceed to the "LP610 blown or visibly burned repair steps" below.

#### Blown 5v supply filter (LP610)
- Always inspect the camera connector/cable on the display if this filter is blown.

- Check camera function with a KNOWN GOOD display.

1. You don't have a board issue until you know you don't have a parts issue. If LP610 measures normally, test with a known good display and display cable, or place the board in a known good housing. If the camera works normally with a different screen/enclosure, the display is the issue and will need to be replaced. BE SURE TO CHECK LP610 FIRST!

### Repair Steps
#### LP610 blown or visibly burned
Understand that this fault occurred because of a catastrophic short within the TCON board of the display. If you replace LP610 without addressing the display issue, LP610 will fail again.

- Generally, when LP610 blows, there will be corresponding pad and trace damage, and jumper wires will usually be required. 36 or 37 AWG enamel-coated copper wire is recommended for jumper wires in this application due to the power requirements of the webcam and ambient light sensor, which are both powered off this filter.

1. The recommended jumper point for the input side of the LP610 (PP5v_S2) is CP717 or RD930. Ensure you have continuity between PP5v_S2 and LP610.
1. Using conformal coating on the jumper wire is strongly recommended.
1. Use a 120 Ohm ferrite filter rated for 1.5 amps in a 402 package size only, preferably from a donor board. Do not substitute a resistor, wire, or fuse.
1. After LP610 is replaced, and jumper wires are run as needed, replace the display assembly or replace the camera connectors on both the cable side and TCON board side on the display. If any internal layer damage is noted to the TCON board or camera cable, replace the display assembly.

  - Only a display for an A2338 MacBook Pro should be used. An older display for an Intel-based MacBook Air will not work and may cause further damage.**
