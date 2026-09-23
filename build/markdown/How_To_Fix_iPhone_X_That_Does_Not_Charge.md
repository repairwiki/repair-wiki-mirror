---
title: "How To Fix iPhone X That Does Not Charge"
pageid: 1565
revid: 3404
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_iPhone_X_That_Does_Not_Charge"
history: "https://repair.wiki/index.php?title=How_To_Fix_iPhone_X_That_Does_Not_Charge&action=history"
permalink: "https://repair.wiki/index.php?oldid=3404"
last_edited: "2024-02-12T07:49:09Z"
contributors:
  - "VCCBoardRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone X"
  - "Stubs"
infobox:
  Device: "IPhone X"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "BGA, Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix iPhone X That Does Not Charge

## Problem description
How To Fix iPhone X That Does Not Charge. For example, you can turn on the phone with a charged battery, but nothing happens when you plug in the charging cable. Or sometimes, it does detect the charging cable, but the battery level keeps dropping. Make sure to confirm if you're having a [No Power](How_To_Fix_iPhone_X_That_Does_Not_Power_On.md) issue or Not Charging issue.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Turns on but doesn't charge
- USB Meter shows 0.000A
- USB Meter shows 0.006A or 0.007A
- Battery level doesn't go up
- Fake charging
- You plug in the charger, you get lightning symbol, but not charging

## Solution
You'll want to first rule out a parts issue:

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
1. In majority of cases, you'll find that replacing Tigris (U3300) will solve charging problems
1. * Tigris will give the common "Tristar" issues that you would see on iPhone 7 and older models.
1. * I would recommend you split the sandwich & test charging with just the top board, battery, charging port and screen.
1. ** If you get 0.006 A or something very low, try replacing Tigris
1. * If it's still not charging, then the next most likely will be the Tigris Coils, L3340 and L3341.
1. ** Replace them and test if it charges with just top board. If it does, then it's solved.
1. In rare cases, Hydra will be the cause of the no charging.
1. * Replace Hydra and see if that solves it.
