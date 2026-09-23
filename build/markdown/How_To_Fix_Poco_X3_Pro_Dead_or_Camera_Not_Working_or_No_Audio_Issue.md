---
title: "How To Fix Poco X3 Pro Dead or Camera Not Working or No Audio Issue"
pageid: 9603
revid: 13875
kind: other
source: "https://repair.wiki/w/How_To_Fix_Poco_X3_Pro_Dead_or_Camera_Not_Working_or_No_Audio_Issue"
history: "https://repair.wiki/index.php?title=How_To_Fix_Poco_X3_Pro_Dead_or_Camera_Not_Working_or_No_Audio_Issue&action=history"
permalink: "https://repair.wiki/index.php?oldid=13875"
last_edited: "2026-02-08T01:13:55Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Poco X3 NFC"
  - "Repair guides for Poco X3 Pro"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix Poco X3 Pro Dead or Camera Not Working or No Audio Issue

## Problem description
Poco X3 and X3 Pro presents with severe system failures such as no power, non-functional cameras, and no audio output. In many cases, the device appears completely dead or fails to boot properly.

When powered via a DC power supply, the phone draws ~0.150 A after a boot prompt and then stalls, indicating that the CPU is attempting to initialize but fails shortly after.

This is a well-known defect on the Poco X3 Pro and is caused by CPU solder joint failure due to thermal stress and board flex.
![Poco X3 (Figure 1) -- Camera not working even after replacing with known good parts](images/0/06/Camera-not-working-poco.webp)

## Symptoms
- No audio (speaker, earpiece, microphone all dead)
- Rear and front cameras not detected / not working
- Device does not power on
- Black screen, no vibration
- Stuck at ~0.150 A on DCPS after pressing power
- No further current ramp (no boot)
- Issue persists after:
  - Replacing battery
  - Replacing screen
  - Replacing cameras or audio components

## Solution
![Poco X3 Pro (Figure 2) -- CPU location](images/0/01/X3-pro-cpu.png)
![Poco X3 Pro CPU (Figure 3) -- CPU reballed](images/0/02/X3-pro-cpu-reballed.png)

### Diagnostic Steps
1. Connect device to DCPS
1. Press power button
1. Observe current behavior:
1. * ~0.150 A stall confirms CPU fault
1. Confirm no shorts on main power rails
1. Rule out:
1. * PMIC failure
1. * Battery fault
1. * Display fault

Once these are ruled out, proceed with CPU repair.
----

### Repair Steps
1. Remove logic board from device
1. Shield surrounding components
1. Preheat board evenly to avoid warping
1. Remove CPU using controlled hot air
1. Clean CPU pads and board pads thoroughly
1. Reball CPU with correct solder size
1. Inspect balls under microscope
1. Reinstall CPU carefully aligned
1. Reflow evenly and allow to cool naturally
1. Clean flux residue
