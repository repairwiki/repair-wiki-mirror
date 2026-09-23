---
title: "MacBook Pro A1989 PP3V3 G3H short repair"
pageid: 133
revid: 487
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1989_PP3V3_G3H_short_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1989_PP3V3_G3H_short_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=487"
last_edited: "2023-10-29T15:25:53Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1989"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1989"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1989 PP3V3 G3H short repair

## Problem description
Missing PP3V3_G3H on A1989 MacBook Pro
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- MacBook not turning on.
- Not charging

## Solution
### Diagnostic Steps
#### Shorted CD3215
Inject 1V to the shorted rail and check with thermal camera which component is heating up, most likely it is one of the CD3215's

#### Corrosion on CB300
If you don't have a short on a CD3215, you probably have corrosion on CB300. If you can't see it, that is because it is hiding under the metal around the NAND.

### Repair Steps
#### Short on one of the CD3215s
Replace the shorted CD3215

#### Corroded CB300
clean the corrosion and replace the capacitor if still shorted.
