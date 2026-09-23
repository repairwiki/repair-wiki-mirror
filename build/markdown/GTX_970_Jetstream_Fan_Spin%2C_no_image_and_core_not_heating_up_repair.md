---
title: "GTX 970 Jetstream Fan Spin, no image and core not heating up repair"
pageid: 855
revid: 2052
kind: repair_guide
source: "https://repair.wiki/w/GTX_970_Jetstream_Fan_Spin,_no_image_and_core_not_heating_up_repair"
history: "https://repair.wiki/index.php?title=GTX_970_Jetstream_Fan_Spin,_no_image_and_core_not_heating_up_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=2052"
last_edited: "2024-01-12T22:56:44Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for GTX 970"
  - "Stubs"
infobox:
  Device: "GTX 970"
  Affects_parts: "Whole board"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# GTX 970 Jetstream Fan Spin, no image and core not heating up repair

## Problem description
Repairing of a likely short on 12V which blew the corresponding fuse on a Jetstream GTX 970.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Not turning on
- No fan spin
- Not detected
- All voltages missing

## Solution
Most likely a problem with a VRM, check if any of the 3 fuses (AF2-10.0V125TM, colored brown, about 6x2.5x2mm and have a capital letter printed on them) are broken. The fuse is most likely broken due to a failure of a mosfet chip, however less likely but still possible, failures of any of the surrounding capacitors/ resistors. A deteriorated thermal pad, causing the aluminum heatsink to short the SMD capacitors is also a possible cause.

[https://www.youtube.com/watch?v=ai8s0Ne8vf8&ab Example video]: (Aluminum short & failed mosfet/inductor)
