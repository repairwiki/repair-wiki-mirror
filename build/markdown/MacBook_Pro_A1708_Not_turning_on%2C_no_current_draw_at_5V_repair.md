---
title: "MacBook Pro A1708 Not turning on, no current draw at 5V repair"
pageid: 170
revid: 403
kind: other
source: "https://repair.wiki/w/MacBook_Pro_A1708_Not_turning_on,_no_current_draw_at_5V_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1708_Not_turning_on,_no_current_draw_at_5V_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=403"
last_edited: "2023-10-27T09:01:54Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1708 Not turning on, no current draw at 5V repair

## Problem description
#incomplete
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- MacBook not turning on
- Drawing 0.00A at 5V (No current draw)

## Solution
PP3V3_G3H is most likely shorted to ground with a 0–1 Ω short, most likely due to bad capacitor. When PP3V3_G3H is directly shorted to ground, it won't produce heat—the PP3V3_G3H power IC is smart enough, usually, when it detects a straight 0 Ω short, to just turn off.
