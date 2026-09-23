---
title: "MacBook Air A1932 Not turning on, pulling very low current at 5V or 20V repair"
pageid: 160
revid: 1298
kind: other
source: "https://repair.wiki/w/MacBook_Air_A1932_Not_turning_on,_pulling_very_low_current_at_5V_or_20V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Air_A1932_Not_turning_on,_pulling_very_low_current_at_5V_or_20V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=1298"
last_edited: "2023-12-02T18:33:16Z"
contributors:
  - "ASRepairs"
anonymous_edits: 1
categories:
  - "Repair guide"
  - "Repair guides for MacBook Air A1932"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Air A1932 Not turning on, pulling very low current at 5V or 20V repair

## Problem description
Diagnosing and resolving issues where a MacBook (820-01521) is pulling very little current at either 5V or 20V as indicated by a USB-C current meter with SLPS2R and AWAKE voltages/signals cycling.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- MacBook not turning on
- Very low current draw at either 5V or 20V
- SLPS2R and AWAKE voltages/signals cycling

## Solution
### Diagnostic Steps
#### Check voltage and resistance to ground on
##### PP5v_G3S
The resistance to ground on PP5v_G3S should fairly high, well within the kilo-ohms. Voltage should be around 5v. Values less than 4.9v should be considered abnormal.

##### PP3v3_G3S
The resistance to ground on PP3v3_G3S should fairly high, well within the kilo-ohms. Voltage should be around 3.3v. Values less than 3.215 should be considered abnormal.

##### PP1v8_G3S
The resistance to ground on PP1v8_G3S should fairly high, well within the kilo-ohms. Voltage should be around 1.8v. Values less than 1.70v should be considered abnormal.

##### PP3v_G3H
The resistance to ground on PP3v_G3H should fairly high, well within the kilo-ohms. Voltage should be around 3.0v. Values less than 2.915 should be considered abnormal.

### Repair Steps
If no shorts were found on the listed rails above, replace U7800.

If you found a short on the listed rails above, inject 1v into the rail and perform thermal imaging. Replace the shorted component.
