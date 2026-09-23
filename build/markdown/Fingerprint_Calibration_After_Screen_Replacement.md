---
title: "Fingerprint Calibration After Screen Replacement"
pageid: 9056
revid: 13500
kind: other
source: "https://repair.wiki/w/Fingerprint_Calibration_After_Screen_Replacement"
history: "https://repair.wiki/index.php?title=Fingerprint_Calibration_After_Screen_Replacement&action=history"
permalink: "https://repair.wiki/index.php?oldid=13500"
last_edited: "2026-01-01T20:40:44Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Missing device page"
  - "Repair guide"
  - "Repair guides for Mi 10 Ultra"
  - "Repair guides for Mi 11 Ultra"
  - "Repair guides for Xiaomi 12"
  - "Repair guides for Xiaomi 12T"
  - "Repair guides for Xiaomi 12X"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Fingerprint Calibration After Screen Replacement

## Problem description
Some Xiaomi devices with in-screen fingerprint sensors may require calibration after a screen replacement otherwise, the fingerprint function will not work.

## Solution
In order to restore the fingerprint fuction we will need a special tool like the ones in the picture below
![667x667px](images/e/ef/Fingerprint_tool.png)
The first step is to acess the Fingerprint calibration tool

Go to Settings > My Device > Detailed Info and Specs.

Scroll down and click on Kernel Version 4 times.

You will enter a special menu called CIT. In the top-left corner, tap the three dots and select the option called *Additional Tools*. This will open a menu named *Additional Tools*. Scroll down until you find an option called **‘FOD Fingerprint Calibration’**, then tap on it.
![Finger Print Option.png](images/8/8a/Finger_Print_Option.png)
⚠️**Before starting, it is recommended to remove any screen protector that may be on the device.**

The tool comes with three silicone rubber pieces. The first one you need is the white one with no grooves.
![535x535px](images/9/95/Rubber_pieces.png)
Place it on top of the sensor as shown, and then click *Start*.
![Step 1.png](images/b/ba/Step_1.png)
If successful, it will now ask for the black rubber piece. Place it on top of the sensor as shown and click *Next*. The screen will turn black for a few seconds.
![Step 2.png](images/8/8b/Step_2.png)
If the test was successful, the final step is to use the white rubber piece with the textured surface. The texture consists of horizontal lines, so make sure you place it correctly aligned; otherwise, the test will fail.

This is where the calibration usually fails most often. If an error occurs, you will need to start from the beginning.

The final step may take multiple tries and can be frustrating. Sometimes you may need to remove the rubber piece from the tool and use your finger on top to apply pressure.

Sometimes, in the final step, you can skip using the tool entirely and use your thumb vertically on the sensor instead — and it may work.

What was found about the error was:

1517 Chart Direction is invalid > The rubber was not aligned perfectly horizontally.

1503 Get calibration failed > The sensor was not covered properly.

1531 polar degree error > This is usually the most frustrating step. The issue can be caused by a pressure problem, shallow grooves, dirt on the tool or display, or sometimes it’s simply a matter of luck.

After a "Test Finished" shows up, restart the device, then you should be able add your fingerprint without any issues.
