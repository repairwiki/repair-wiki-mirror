---
title: "Rampage V Does not POST, reboots every few seconds repair"
pageid: 1516
revid: 3321
kind: repair_guide
source: "https://repair.wiki/w/Rampage_V_Does_not_POST,_reboots_every_few_seconds_repair"
history: "https://repair.wiki/index.php?title=Rampage_V_Does_not_POST,_reboots_every_few_seconds_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=3321"
last_edited: "2024-02-04T14:21:05Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for ROG Rampage V Extreme"
  - "Stubs"
infobox:
  Device: "ROG Rampage V Extreme"
  Affects_parts: "Main Board"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Rampage V Does not POST, reboots every few seconds repair

## Problem description
Fixing an issue where the Rampage V does not POST and restarts every few seconds.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Continuous reboots
- No POST

## Solution
Generally caused by lack of power on some rail. Check memory inductor (should be 1.25V), southbridge inductor (should be 1.05V).

One case had the culprit being a faulty RT8065 step-down converter near southbridge power phase - common problem on ASUS boards, [https://www.youtube.com/watch?v=cN4toTZZ2Ww example video]
