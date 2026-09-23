---
title: "Mean Well RSP-2000-48 Not turning on at all repair"
pageid: 2146
revid: 4459
kind: repair_guide
source: "https://repair.wiki/w/Mean_Well_RSP-2000-48_Not_turning_on_at_all_repair"
history: "https://repair.wiki/index.php?title=Mean_Well_RSP-2000-48_Not_turning_on_at_all_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=4459"
last_edited: "2024-07-18T12:59:40Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Mean Well RSP-2000-48"
infobox:
  Device: "Mean Well RSP-2000-48"
  Affects_parts: "Fuse, MOSFETs."
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Mean Well RSP-2000-48 Not turning on at all repair

## Problem description
Fixing a Mean Well power supply that doesn't react to power at all when plugged in. This particular issue is rather common and is cased by a faulty fuse that connects the out of the PFC (power factor correction) to the bulk DC capacitors. Mostly, this fuse is blown by heat or a spike in load where upon replacing it the PSU works fine afterwards. Other cases have the switching [MOSFETs](Transistors_-_Repair_Basics.md) become [shorted](Short_Circuits_-_Repair_Basics.md) Which blows the fuse.

![Blown fuse 10A at 250V (figure 1)](images/5/53/20240319_111318.jpg)

## Symptoms
- Not turning on
- Not reacting to power
- - ==Solution==

### Diagnostic Steps
- Open up the device and take out the pcb.
- Measure the fuse on figure 1, if it's blown open the continue with the guide, otherwise, you have a different problem!
- Measure the bulk caps if there's a short, if there is, you'll need to find out which component is causing it.
- Since all the MOSFETs are placed on a heatsink, it'll be hard to detect which is shorted with voltage injection, what I did was cut the legs and measure again, if it's not the cause of the short I solder the legs back.
- Once you've identified the short, proceed to the repair steps

### Repair Steps
- If you had no short on the bulk caps, replace the fuse and test. It should work afterwards. If it doesn't and blows again even without a short that means the driving for the MOSFETs is faulty.
- If you had a short and successfully identified which is causing it, replace that component and the fuse.
-
