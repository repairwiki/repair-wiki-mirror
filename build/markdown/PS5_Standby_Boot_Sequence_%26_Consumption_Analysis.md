---
title: "PS5 Standby Boot Sequence & Consumption Analysis"
pageid: 8819
revid: 12839
kind: explanatory_guide
source: "https://repair.wiki/w/PS5_Standby_Boot_Sequence_%26_Consumption_Analysis"
history: "https://repair.wiki/index.php?title=PS5_Standby_Boot_Sequence_%26_Consumption_Analysis&action=history"
permalink: "https://repair.wiki/index.php?oldid=12839"
last_edited: "2025-11-23T07:51:29Z"
contributors:
  - "VCCBoardRepairs"
  - "Ben ProFixerr"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for PlayStation 5"
  - "Explanatory guides for PlayStation 5 Pro"
  - "Explanatory guides for PlayStation 5 Slim"
infobox:
  Device: "PlayStation 5, PlayStation 5 Pro, PlayStation 5 Slim"
  Type: "Troubleshooting/Diagnostics"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# PS5 Standby Boot Sequence & Consumption Analysis

## 🔌 PS5 Resting Power Consumption Using DCPS
Checking the resting power draw with a DCPS helps determine the console’s current health.

A DCPS (bench power supply) should be set to **12V / 2A** and used to inject power into the **12V rail** of the PS5.

Below is what different resting consumption levels may indicate, but first—here’s how to connect it properly.
----

### 📎 How to Connect the Power Supply
1. Set voltage to **12V**
1. Set amperage to **2A**
1. **Turn OFF** the power supply
1. Attach clips to the board prongs
1. **Turn ON** the power supply and monitor consumption for **10–15 seconds**

----

### 📊 What Healthy Readings Look Like
- Amperage climbs to **~0.321A** for a few seconds
- Then drops to **~0.007A**

This suggests the console is likely in good condition.
----*Data sourced from FixMyApp Research* ✔️

| First Stage | Second Stage | Potential Cause |
| --- | --- | --- |
| +- 321 mA | +- 7 – 10 mA | WORKING / GOOD |
| +- 0.0 mA | +- 0.0 mA | Check BIOS and fuses, +12V power supply, Check for short on the +12V input |
| +- 0.015 mA | +- 0.015 mA | Check for shorts near Soutbridge IC |
| +- 5 mA | +- 5 mA | Check for shorts near HDMI encoder IC |
| +- 7 mA | +- 27 mA | Check for shorts near Soutbridge IC |
| +- 7 mA | +- 7 mA | When console get’s standby power if it is stuck at 7mA. Check the voltages of Dialog ic and frequency of the 25Mhz clock and the 32Khz clock of the Southbridge IC. If that is working, try to see if the Southbridge is accessing the BIOS IC. Flash firmware / Replace the BIOS IC, Southbridge IC |
| +- 7 mA (boot loop) | +- 12 mA | Check for short on the 1.1V power rail |
| +- 24 mA | +- 7 mA | Check fuses and check for shorts |
| +- 35 mA | +- 35 mA | Check for shorts on the 1.9V power rail |
| +- 58 mA | +- 7 mA | Check fuses and check for shorts |
| +- 175 mA | +- 10 mA | Check SSD Controller for shorts |
| +- 225 mA | +- 7 mA | Check SSD Controller for shorts |
| +- 270 mA | Current goes down when you press power and you hear a beep | Check for shorts near the Wifi IC |
| +- 315 mA | +- 315 mA | Check 3.3V STBY power rail present, check for shorts Wifi IC |
| +- 321 mA | +- 7 – 10mA (it goes fast to sleep) | Check SSD controller. Sometimes you get an update screen or no power behaviour |
