---
title: "Samsung Galaxy A53 5G Network issue"
pageid: 4537
revid: 7594
kind: repair_guide
source: "https://repair.wiki/w/Samsung_Galaxy_A53_5G_Network_issue"
history: "https://repair.wiki/index.php?title=Samsung_Galaxy_A53_5G_Network_issue&action=history"
permalink: "https://repair.wiki/index.php?oldid=7594"
last_edited: "2025-06-12T21:19:02Z"
contributors:
  - "Ajimalg82"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Galaxy A53 5G"
  - "Stubs"
infobox:
  Device: "Galaxy A53 5G"
  Affects_parts: "Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering, BGA"
  Difficulty: "4. Specialist"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Samsung Galaxy A53 5G Network issue

## Problem description
In this condition, your phone experiences severe network issues. You may notice one or more of the following:

- No network service.
- Only emergency calls are possible.
- Complete inability to make or receive calls.

## Symptoms
- The phone continuously switches between "Emergency Calls Only" and "No Service."
- Sometimes signal bars appear, but they are only for emergency calls.
- Occasionally, a blocked or crossed-out icon replaces the signal bars.
- Flight Mode can be toggled normally (the button is not greyed out or stuck).

- You can manually switch between different network modes (2G, 3G, 4G, 5G), but the problem remains.

### Root Cause
The issue is usually caused by a malfunctioning or shorted **APT IC** located near the CPU. When the APT IC fails or operates inconsistently, it disrupts the network power supply (VPA_APT), leading to unstable or no network service.

## Solution
There are 2 ways to fix this issue:

1. Replace the ic.
1. Bypass the ic but not by removing it

![front network section](images/a/aa/PA_front_side.png)

## Diagnostic Steps
1. **Check for Shorts:**
1. * Inspect the area around the network-related ICs for short circuits (see the image)
1. **Measure VPA_APT Output:**

![VPA_APT COIL](images/c/c8/VPA_APT.png)

- Probe the VPA_APT coil output (in the picture)
- The expected voltage should be in the range of **2.0V to 4.2V** (depending on battery voltage)
- If the reading is **0.00V** or fluctuates continuously, proceed to repair steps

### Repair Steps
#### Solution 1: **Replace the APT IC**
![VPA_APT IC](images/8/80/VPA_APT_ic.png)

- Remove the shield covering the IC.
- Desolder and remove the faulty APT IC(shown in the picture)
- Inspect the PCB pads for any damage.
  - If pads are intact, proceed.
- Reball the replacement APT IC using **183°C (medium-temp	solder paste)**.
- Install and solder the new IC onto the board.

- Verify the repair by checking network functionality.

#### **Solution 2: Bypass the APT IC (Jumper Method)**
![VPA_APT to VPH_PWR JUMPER](images/b/b2/Jumper_vpa_apt_to_vph_power.png)

- Locate the **VPH_PWR** point on the motherboard (shown in the picture)
- If the APT IC is burnt, first remove the **VPA_APT boost coil**.
- Create a jumper wire connecting **VPH_PWR** to the **VPA_APT output** (refer to image for exact points).
- Apply solder mask to secure the jumper and prevent shorts.

- Test the phone’s network functionality.
