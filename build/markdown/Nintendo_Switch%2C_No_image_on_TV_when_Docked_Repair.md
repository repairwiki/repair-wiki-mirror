---
title: "Nintendo Switch, No image on TV when Docked Repair"
pageid: 913
revid: 2228
kind: repair_guide
source: "https://repair.wiki/w/Nintendo_Switch,_No_image_on_TV_when_Docked_Repair"
history: "https://repair.wiki/index.php?title=Nintendo_Switch,_No_image_on_TV_when_Docked_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=2228"
last_edited: "2024-01-13T16:35:25Z"
contributors:
  - "ASRepairs"
  - "HaileyKitty"
anonymous_edits: 0
categories:
  - "Stubs"
infobox:
  Device: "Nintendo Switch"
  Affects_parts: "Main Logic Board"
  Type: "Soldering, Part replacement"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Nintendo Switch, No image on TV when Docked Repair

## Problem description
Fixing an issue where the Nintendo Switch shows no image on TV when Docked

## Symptoms
- No image on TV when Docked

## Solution
- Check if the port is damaged on Switch and the dock, try replacing the port, may be loose or improperly soldered.
- Try replacing P13USB.
- Check ferrite chokes/beads between P13USB and the port for continuity, check capacitors between as well. Try replacing all of them, even if they look OK.
- Sometimes replacing M92T36 will fix it, especially if the console also has charging issues like for example charging from just one side.
- Otherwise it may be a tricky case to solve as these data lines are high frequency and sensitive, sometimes it's not always solvable unless you have a good high frequency oscilloscope and are familiar with USB-C/HDMI video out communication protocols.
