---
title: "Epson ELPDC21 Not turning on, led blinking"
pageid: 1087
revid: 2532
kind: repair_guide
source: "https://repair.wiki/w/Epson_ELPDC21_Not_turning_on,_led_blinking"
history: "https://repair.wiki/index.php?title=Epson_ELPDC21_Not_turning_on,_led_blinking&action=history"
permalink: "https://repair.wiki/index.php?oldid=2532"
last_edited: "2024-01-14T15:59:38Z"
contributors:
  - "Pandrew"
anonymous_edits: 0
categories:
infobox:
  Device: "Epson ELPDC21"
  Affects_parts: "Connectors"
  Needs_equipment: "Screwdrivers"
  Type: "Teardown"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Epson ELPDC21 Not turning on, led blinking

## Problem description
When the main board of the document camera cannot talk to the camera head, it will not finish its startup sequence.

## Symptoms
Detail all measurable or observable symptoms in this section.

- After pressing the power button the power led correctly starts flashing, but
- The flashing never stops, and the document camera doesn't start functioning

## Solution
### Diagnostic/Repair Steps
![Figure 1 - The first connector to check](images/0/01/Epson_elpdc21_document_camera_reseat_this_connector_first.jpg)
![Figure 2 - The second connector to check](images/7/71/Epson_elpdc21_document_camera_reseat_this_connector.jpg)
The most likely reason this can happen is that one of the connectors gets disconnected, either on the main board, or in the camera head. The connector in the camera head is more likely to become disconnected, however as a first step it's recommended to check the connector at the main board, because it's easier to disassemble the base of the camera.

Diagnostics and repair involves disassembling the device, and re-seating the connector.

1. Disassemble the base of the device
1. Check and re-seat the connector on Figure 1
1. If the device still doesn't turn on, then:
1. Re-assemble the base
1. Disassemble the camera head (this is more difficult)
1. Check and re-seat the connector on Figure 2
1. If the device still doesn't turn on, then it may have a more complicated fault
