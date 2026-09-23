---
title: "MacBook Pro A2289 Not turning on, fluctuating current draw 0.03-0.1A at 20V repair"
pageid: 81
revid: 530
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A2289_Not_turning_on,_fluctuating_current_draw_0.03-0.1A_at_20V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A2289_Not_turning_on,_fluctuating_current_draw_0.03-0.1A_at_20V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=530"
last_edited: "2023-10-29T15:29:14Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A2289"
  - "Stubs"
infobox:
  Device: "MacBook Pro A2289"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A2289 Not turning on, fluctuating current draw 0.03-0.1A at 20V repair

## Problem description
This issue is often caused by a short to ground on a sub-rail, which can be accurately detected with a high resolution thermal imaging scan. Low resolution thermal imaging may not reveal the subtle signs of a small shorted component, making it a less reliable diagnostic method.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- No power
- No fan spin
- All voltages missing

## Solution
If the issue has a single, specific solution, provide it in this section and delete the sub-headers below. Otherwise, if there are multiple potential causes for the problem, outline the process of identifying the root cause and offer corresponding solutions below.

### Diagnostic Steps
- Perform High Resolution, High Sensitivity thermal imaging of the entire system board.
  - Low resolution thermal imagers will likely not pick up the subtle temperature changes failures like this often present with.
  - The failure will often present as a component quickly heating up and cooling down in sync with the amperage changes; Occasionally, you will find a resistor heating up/cooling down in sync with the amperage changes.
  - The short is likely caused by something on the output side of the resistor.

### Repair Steps
- Remove and Replace the shorted component based on thermal imaging findings.
