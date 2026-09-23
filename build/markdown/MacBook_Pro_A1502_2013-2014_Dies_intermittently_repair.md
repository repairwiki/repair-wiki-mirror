---
title: "MacBook Pro A1502 2013-2014 Dies intermittently repair"
pageid: 495
revid: 1032
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1502_2013-2014_Dies_intermittently_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1502_2013-2014_Dies_intermittently_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=1032"
last_edited: "2023-11-08T18:09:57Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1502"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1502"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1502 2013-2014 Dies intermittently repair

## Problem description
Intermittently dead, no current draw or magsafe in fault condition
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Works but sometimes dies.

## Solution
SMC inactive, however not in reset etc. No clock activity noted on an oscilloscope. SMC_XTAL measured 1k to ground (should be in the megaohms). Tried replacement Y5110 from a donor and then SMC_XTAL measured 3 Megaohms. But this went back to 1k when the board fully cooled down. Reflowed the SMC and this resolved it. This board appears to be have been in an ultrasonic at another shop and likely had crap underneath it. Ultrasonic can't really do much under a BGA with edge bonding around it.
