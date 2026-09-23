---
title: "IPhone XS Not Charging"
pageid: 4590
revid: 7652
kind: repair_guide
source: "https://repair.wiki/w/IPhone_XS_Not_Charging"
history: "https://repair.wiki/index.php?title=IPhone_XS_Not_Charging&action=history"
permalink: "https://repair.wiki/index.php?oldid=7652"
last_edited: "2025-06-13T23:30:28Z"
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

# IPhone XS Not Charging

## Problem description
iPhone XS will turn on but does not charge
![iPhone Xs Yangtze location on bottom side of top board](images/5/5e/Screenshot_From_2025-06-13_16-27-28.png)

## Solution
If the phone turns on but doesn't charge, you'll want to first rule out a parts issue:

- Unplug everything, ear speaker flex, power button flex, cameras, antennas, etc.
- Only leave the screen, charging port and battery, then test again
- If still not charging, test with a known good charging port, battery and screen.

  - Troubleshooting & Solutions:**

1. Sometimes, the ear speaker flex, which has a flood illuminator (for Face ID) and ALS sensor (for auto brightness and true tone), will get liquid damaged
1. * These sensors sit right by where the ear mesh is located and it's super easy for liquid to sneak into the phone and get on these sensors. The corrosion will short data lines underneath them and cause bootlooping, not charging and other random issues.
1. * If this is the case, you can either
1. ** Replace the flex and lose Face ID
1. ** Or safely remove the flood illuminator off the flex, clean off the corrosion and place it back
1. ** Or sometimes the flex is damaged beyond repair, so you can swap the sensors to a new flex.
1. In majority of cases, you'll find that replacing Yangtze (U3300) will solve charging problems
1. * Yangtze will give the common "Tristar" issues that you would see on iPhone 7 and older models.
1. * I would recommend you split the sandwich & test charging with just the top board, battery, charging port and screen.
1. ** If you get 0.006 A or something very low, try replacing Yangtze
1. In rare cases, Hydra will be the cause of the no charging.
1. * Replace Hydra and see if that solves it.

- Migrated from old wiki*
