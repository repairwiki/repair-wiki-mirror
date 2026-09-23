---
title: "IPhone X image no centered and iphone restarting"
pageid: 5640
revid: 8911
kind: other
source: "https://repair.wiki/w/IPhone_X_image_no_centered_and_iphone_restarting"
history: "https://repair.wiki/index.php?title=IPhone_X_image_no_centered_and_iphone_restarting&action=history"
permalink: "https://repair.wiki/index.php?oldid=8911"
last_edited: "2025-07-21T23:11:19Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone X"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone X image no centered and iphone restarting

## Problem description
The iPhone turns on but the Apple logo is not centered on the display, and it may also display some weird graphics.
![Logo on the right side](images/7/7b/Logo_on_right_side.jpg)

## Symptoms
- Apple logo not centered
- Apple logo not centered and iphone restarting
### Diagnostic Steps
The first step is always try a new screen to make sure you dont have a parts problem.

If a new display does not fix the issue the next step is to inspect the LCD FPC for any physical damage.

If you have the Apple logo on the right side your issue is likely caused by a faulty coil (L2780) a GPU line (BUCK8_LX0).

If the Apple logo is in the lower part of the display your issue is most likely caused by a open filter (FL5780) on the line PP1V8_DISPLAY_CONN.

### Repair Steps
If the Logo in on the right side of the screen we must replace L2780 this is a common issue on the iPhone X, the coil is located on the top board next to the CPU.
![L2780 Location](images/4/4b/L2780_Location.png)

1. Split the boards using your preferred method.
1. Locate and inspect the coil L2780 for any cracks.
1. Replace the coil you can get one from a donor motherboard or buy a new one here is the specs **1UH-20%-2.5A-0.052OHM**
1. Test the motherboard on tool like and Isocket to confirm the issue is fixed.
1. Reball the bottom board and solder the boards back together.

If the logo is on the bottom part of the screen like in the image bellow the issue is with the PP1V8_DISPLAY line.
![Logo on the bottom part of the screen](images/d/da/Logo_on_the_bottom_part_of_the_screen.png)

1. Locate FL5780 is located near the LCD FPC

![FL5780 Location](images/4/4f/FL5780_Location.png)

1. 1. Replace the filter you can grab one from a donor board or buy new one here is the specs: **33-OHM-25%-1500MA.**

Note if you dont have a filter on hand you can make a small jumper to test if it fixes the issue.

## Final Testing
After doing the repair if you had to split the board make sure to test every function of the device.

Make sure the display can produce image like expected.
