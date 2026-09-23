---
title: "Xbox One S No Power"
pageid: 4996
revid: 8125
kind: other
source: "https://repair.wiki/w/Xbox_One_S_No_Power"
history: "https://repair.wiki/index.php?title=Xbox_One_S_No_Power&action=history"
permalink: "https://repair.wiki/index.php?oldid=8125"
last_edited: "2025-06-29T22:45:57Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Xbox One S"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Xbox One S No Power

## Problem description
The Console does not turn on.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- The console does not turn on

### Diagnostic Steps
Usually an Xbox that shows no signs of life is due to a missing standby voltage.

The first voltage required is 12V, this line is produced from the power supply.

Connect your power supply to the motherboard and then to mains power with your multimeter measure the test point shown on the image below.
![Xbox One S 12V input](images/a/a6/Xbox_One_S_12V_input.png)
If 12V is good we know the problem is not caused by the PSU.

The next important line to check is the 5V it is common to have a short here.
![Xbox One S 5V Line](images/f/f6/Xbox_One_S_5V_Line.png)
The next line to check is 1.1V
![Xbox One S 1.1V Standby](images/3/31/Xbox_One_S_1.1V_Standby.png)

The next line to check is 1.8V
![Xbox One S 1.8V Standby](images/6/66/Xbox_One_S_1.8V_Standby.png)
The last main standby voltage to check is 3.3V
![Xbox One S 3.3V Standby](images/1/17/Xbox_One_S_3.3V_Standby.png)

### Repair Steps
If you find a shorted line on the motherboard with your DCPS inject a voltage into that rail and monitor the board under a thermal camera the component that is shorted will heat up. Be careful not to inject a higher voltage than the line is rated for.

If you find a shorted line on the motherboard with your DCPS, inject a voltage into that rail and monitor the board under a thermal camera, the component that is shorted will heat up. Be careful not to inject a higher voltage than the line is rated for.
![Shorted U4C3](images/3/39/Shorted_U4C3.png)
If 12V is missing and the line is not shorted replace the PSU.

If 5V is missing and is not shorted replace U4C3.

If 1.1V is missing and is not shorted replace U4D4.

If 1.8V is missing and is not shorted replace U3D6.

If 1.8V is missing and is not shorted replace U4C2.

## Final Testing
After repairing the console, make sure it turns on fully and runs a game.
