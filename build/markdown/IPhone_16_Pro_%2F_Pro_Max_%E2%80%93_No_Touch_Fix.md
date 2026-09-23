---
title: "IPhone 16 Pro / Pro Max – No Touch Fix"
pageid: 6733
revid: 10207
kind: repair_guide
source: "https://repair.wiki/w/IPhone_16_Pro_/_Pro_Max_%E2%80%93_No_Touch_Fix"
history: "https://repair.wiki/index.php?title=IPhone_16_Pro_/_Pro_Max_%E2%80%93_No_Touch_Fix&action=history"
permalink: "https://repair.wiki/index.php?oldid=10207"
last_edited: "2025-08-14T06:45:09Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 16 Pro"
  - "Repair guides for iPhone 16 Pro Max"
infobox:
  Device: "iPhone 16 Pro, iPhone 16 Pro Max"
  Affects_parts: "Main Logicboard"
  Needs_equipment: "Microscope, soldering equipment"
  Difficulty: "3. Hard"
  Type: "Soldering"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 16 Pro / Pro Max – No Touch Fix

## Problem Description
iPhone 16 Pro or Pro Max boots normally and display turns on, but touch is completely unresponsive. This issue stems from a shorted or disconnected signal on the IO_AP_TOUCH_BSYNC1 line, which is responsible for touchscreen communication.

## Symptoms
- Screen lights up, no touch response.
- Replacing the display does not fix the issue.

## Diagnostic Steps
1. Locate IO_AP_TOUCH_BSYNC1 line on display connector (J11800) and measure its diode value.
1. If line shows OL, it’s disconnected.
1. If line shows 0.000V or close to GND, it’s shorted internally to CPU.

[[File:Jumper-point-display-connector.png|thumb|Jumper location on the display connector [J11800] - figure 1]]

## Repair Steps
#### Case 1: Line is Disconnected (OL)
<blockquote>IO_AP_TOUCH_BSYNC1 line is broken/open between CPU and filter.</blockquote>

1. Locate the capacitor (C11727) connected to IO_AP_TOUCH_BSYNC1 line.
1. Find IO_AOP_TO_ALS_BSYNC2_CONN on the front prox connector (C11147) (see fig. 2)
1. Run a jumper wire from that point on the front prox connector to the output side of the removed filter pad.
1. Clean up, reassemble, and test — Touch should now be restored.

----
[[File:Jumper-point-prox-connector.png|thumb|Jumper location on the prox connector [J11100] - figure 2]]

#### Case 2: Line is Shorted Internally in CPU
<blockquote>IO_AP_TOUCH_BSYNC1 shows 0V or is shorted to ground.</blockquote>

1. Disconnect the IO_AP_TOUCH_BSYNC1 pad on the display connector to isolate the short.
1. Confirm that the line is no longer shorted beyond the capacitor.
1. Run a jumper wire from IO_AOP_TO_ALS_BSYNC2_CONN on the Front Prox Flex connector (J11100) to the display connector (J11800). (see fig. 1)
1. Clean up and test — Touch should be restored.

![Jumper location on the display connector - BoardView](images/7/7c/Jumper-point-display-connector-boardview.png)

![Jumper point on the prox flex connector - Boardview](images/f/f3/Jumper-point-prox-connector-boardview.png)
