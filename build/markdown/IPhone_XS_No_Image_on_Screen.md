---
title: "IPhone XS No Image on Screen"
pageid: 4595
revid: 7659
kind: repair_guide
source: "https://repair.wiki/w/IPhone_XS_No_Image_on_Screen"
history: "https://repair.wiki/index.php?title=IPhone_XS_No_Image_on_Screen&action=history"
permalink: "https://repair.wiki/index.php?oldid=7659"
last_edited: "2025-06-14T00:05:26Z"
contributors:
  - "Samhext"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone XS"
  - "Repair guides for IPhone XS Max"
  - "Stubs"
infobox:
  Device: "IPhone XS, IPhone XS Max"
  Affects_parts: "Motherboard"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone XS No Image on Screen

## Problem description
iPhone XS & XS Max uses an OLED display. This mean, there's no backlight, but many people will still diagnose No Image as "No Backlight".

Always make sure to test with a known good screen, to rule out a parts issue.
![iPhone Xs Boardview of display FPC with FL5783 circled in red and display chokes circled in green](images/b/b7/Screenshot_From_2025-06-13_16-42-18.png)

## Symptoms
- Phone turns on but nothing displays on the screen
- Screen always stays black
- You can hear sounds & feel vibrations.

## Solution
- Diode mode the display connector (J5700) & check for any shorts or OL (Open Lines).
- In most cases, you'll find PP3V0_DISPLAY_CONN filter FL5783 is blown & needs to be replaced.
- In other cases, you may find one or more of the 5 chokes L5700, L5710, L5730, L5740 or L5720 is damaged or broken from pry damage
- In rare cases, you may discover there is long screw damage in the screw hole next to the battery connector, which will sever image lines from the chokes mentioned above.
