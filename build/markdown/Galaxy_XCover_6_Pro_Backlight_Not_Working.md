---
title: "Galaxy XCover 6 Pro Backlight Not Working"
pageid: 4575
revid: 7635
kind: repair_guide
source: "https://repair.wiki/w/Galaxy_XCover_6_Pro_Backlight_Not_Working"
history: "https://repair.wiki/index.php?title=Galaxy_XCover_6_Pro_Backlight_Not_Working&action=history"
permalink: "https://repair.wiki/index.php?oldid=7635"
last_edited: "2025-06-13T07:54:05Z"
contributors:
  - "Samhext"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Galaxy XCover 6 Pro"
  - "Stubs"
infobox:
  Device: "Galaxy XCover 6 Pro"
  Affects_parts: "Motherboard"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Galaxy XCover 6 Pro Backlight Not Working

## Problem description
Samsung Galaxy XCover 6 Pro backlight is not working but phone still turns on normally, makes sounds, and when holding a flashlight up to the screen you are still able to make out that the LCD is on and working aside from the backlight being out.
![Figure 1, Samsung Galaxy XCover 6 Pro backlight circuit location](images/2/29/IMG_5074.JPEG)

## Symptoms
- While phone is turning on, hold a flashlight up to the display and you should be able to make out a very faint Samsung logo
- Phone turns on, charges normally, makes sounds and otherwise works normally aside from the backlight not working

## Solution
- First you will want to test device with another screen as the backlight problems can be caused by a faulty display, especially in cases of water damage where a majority of the corrosion and liquid damage was confined to the screen itself.
- If a known good screen does not fix the problem then move on to checking the display FPC connector for any damage, including loose pins, broken or warped plastic on the connector etc.  If any damage is found you will first want to replace the FPC and test again. At this point if both the FPC connector and the screen itself have been ruled out we can move on to looking at the backlight circuit itself.

![Figure 2, Samsung Galaxy XCover 6 Pro backlight circuit schematic](images/1/13/Att.3gmiQEKGW_8P1p4R2gcP3SePmTb9Akspn2fx2vSW_Pg.jpg)
![Figure 3, Samsung Galaxy XCover 6 Pro Backlight circuit layout](images/e/e1/Att.3YWnH4cNHAZWgkOYAg8WSfF_kM-XlLDUfhVZQksSCrk.jpg)

In figures 2 & 3 we can go over the backlight circuit schematic and layout of components.  In figure 2, we see that the LED_A_24P is the output line that goes to the main display FPC and what supplies power to the display backlight panel so let's focus on the components that are on this line.  The main components on this line will be the L9001 coil, which connects to diode D9000, then travels through several smoothing capacitors, until reaching L9032 and after one more cap outputs to the display.

- In order to test and determine which component(s) on this line are causing our problem we will need to first get under the shield covering the components.  Refer to Figure 1 for the location of components in Figure 3 on the back side of the board under where the sim tray flex normally sits.
  - The easiest way to uncover the backlight circuit will be using a grinder and shears to cut a chunk of the shield off over the top of the backlight circuit components.  Make sure to not cut too deeply into the shield otherwise you might cut into and damage components that were otherwise functional.
  - If you do not have a grinder, then add low melt solder to the perimeter of the entire shield whit your iron, and then use a hot air station with high heat and airflow to lift the entire shield off of the board.  This would not be the preferred method compared to using a grinder since it is a very large shield which will need a lot of heat to remove and the CPU is on the opposite side of the board to this shield which means there will be a high risk to floating the CPU
- In my case, after removing the part of the shield covering the backlight circuit I found the L9001 coil to be burnt and have no continuity through it.  If L9001 is fried then you will need to replace it.  Either you will need to source the coil from another XCover 6 Pro donor board, or look for a coil on another donor board that is the same size and type.
  - If you need to source the coil from a different model try to find one used in another backlight circuit as most samsungs with an LCD have very similar components to each other.
  - You can also check the potential replacement coil's specs in ZXW or JCDrawing to make sure they line up with the XCover 6 Pro L9001 rating of 10uH
  - If you can't find another the exact coil from another samsung backlight circuit or exact specs, just look for one a coil that looks identical to L9001 and it should work
- As you may already know even if the coil is burnt that will almost never be the only problem since a coil is essentially a long wire and has a very low chance of burning up on its own so we will need to keep looking at the rest of the components on this line to figure out what caused L9001 to fry.
- Next on the line will be D9000.  To check this put your multimeter in diode mode and place your red probe on one side of the diode, and the black probe on the opposite side of the diode.  Since diodes are designed to only have continuity in one direction we should either get a low reading (like 0.250V etc) or a very high reading or OL.  Now switch your probes to the opposite sides you just measured and you should get the opposite multimeter reading of what you just measured.  If both sides read similar to each other then the diode is bad and will need to be replaced.
  - Like the coil you can pull a replacement diode from a donor XCover 6 Pro board or an ipad 5 backlight diode will work as a suitable replacement.
- Finally we will want to check all of the smoothing capacitors.  Make sure to test these even if you've replaced either a faulty D9000 or L9001 as a shorted capacitor will likely cause your replacement coil or diode to get fried again.
- Put your multimeter into diode mode and then place your red probe on ground, and place your black probe on both sides of one of the six smoothing caps that come after D9000 (C9004, C9005, C9020, C9021, C9030, and C9031).  If both sides read 0.000V then one of the caps is shorted and will need to be removed.
  - Check for any caps that look cracked, heavily discolored, or burnt as this will be a telltale sign that that is the cap which is shorted.
  - If none of the caps are visibly bad, then you will need to use a power supply and a thermal camera or freeze spray to find the shorted cap.
  - Set your DCPSU to something low like 1v, 2-3a and place your black probe on ground and your red probe on any of the side opposite to ground on any of the caps, then pay attention to your thermal camera to find which cap is heating up.  (If you use freeze spray pay attention to which cap melts first)
  - You will then need to remove the cap that either looks visibly broken or the one that is heating up when voltage is injected into the line, use a blade or similar tool to break the cap off, it should lift off the board pretty easily.
  - After removing the cap use your multimeter to again test and make sure you no longer have a short to ground on both sides of the caps on the backlight power line.
- Finally plug everything back in and test.  It is not uncommon to fix the backlight circuit and find that the display is also not working so if you have removed the short and backlight is still not working, test with a known good screen again.
