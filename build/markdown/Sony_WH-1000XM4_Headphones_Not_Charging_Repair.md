---
title: "Sony WH-1000XM4 Headphones Not Charging Repair"
pageid: 1436
revid: 3152
kind: repair_guide
source: "https://repair.wiki/w/Sony_WH-1000XM4_Headphones_Not_Charging_Repair"
history: "https://repair.wiki/index.php?title=Sony_WH-1000XM4_Headphones_Not_Charging_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3152"
last_edited: "2024-01-22T16:21:23Z"
contributors:
  - "KevinShort"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for WH-1000XM4"
  - "Stubs"
infobox:
  Device: "WH-1000XM4"
  Affects_parts: "Charging port board"
  Needs_equipment: "Screwdriver, pry tools"
  Type: "Part replacement"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Sony WH-1000XM4 Headphones Not Charging Repair

## Problem description
Diagnosis and repair of WH-1000XM4 headphones that will not charge.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Headphones will not charge the battery.
- Charging light may not turn on or may flash repeatedly.

## Solution
- NO CHARGING LIGHT  -  If the red charging light does not come on when plugging headphones into a known-good charger, test again with known-good USB_R board (aka USB-C port board, charging port board)  (IMPORTANT NOTE: The service manual says "It is not possible to replace the USB R board only." but that is NOT TRUE! I have successfully replaced dozens of these and it's not difficult!)

- YES CHARGING LIGHT  -  If the red charging light does come on but flashes red-red---red-red--- (repeatedly flashes twice in red), this indicates a thermal issue was detected. There could be an actual thermal issue (worth investigating, especially if it's a custom device!), or the THM_R "board" could be damaged or defective, or (*most likely*) the connector on the SUB_R board where the THM_R plugs in is damaged (very common, these have very weak solder joints)

- NOTE: When the WH-1000XM4 has a charging problem, it's always either the SUB_R board (or it's components), the USB_R board or both.
