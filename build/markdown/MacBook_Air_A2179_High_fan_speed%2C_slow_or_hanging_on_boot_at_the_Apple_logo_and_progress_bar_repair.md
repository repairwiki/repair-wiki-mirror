---
title: "MacBook Air A2179 High fan speed, slow or hanging on boot at the Apple logo and progress bar repair"
pageid: 88
revid: 208
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Air_A2179_High_fan_speed,_slow_or_hanging_on_boot_at_the_Apple_logo_and_progress_bar_repair"
history: "https://repair.wiki/index.php?title=MacBook_Air_A2179_High_fan_speed,_slow_or_hanging_on_boot_at_the_Apple_logo_and_progress_bar_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=208"
last_edited: "2023-09-27T17:08:16Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Stubs"
infobox:
  Device: "MacBook Air A2179"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering, Part replacement, Cleaning"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Air A2179 High fan speed, slow or hanging on boot at the Apple logo and progress bar repair

## Problem description
When turning on the MacBook, the fan speed ramps up and gets stuck on the apple logo with progress bar.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Fast loud fan
- Very slow or stuck on apple logo and progress bar

## Solution
### Diagnostic Steps
#### Check if the battery cable is fully seated into the battery connector
The cable should "click" into the connector. A partially seated battery connector is a common occurrence among technicians unaccustomed to working on the newer MacBook Air devices.

#### Boot into Apple Diagnostics by holding the D key on startup
- Apple Diagnostics may display a *"There may be an issue with the System Management Controller (SMC)"* error.
  - This error seldom indicates a board issue on A1932 devices and usually indicates an issue with the battery, or any of the device's thermal sensors, most commonly the palm-rest sensor located in the trackpad.
- If you're unable to access Apple Diagnostics as the device will hang after you enter your WiFi password to boot into diagnostics or it displays no errors, proceed to "Unable to access Apple Diagnostics" in repair steps below.

#### Inspect the mainboard for corrosion
Carefully observe the the logic board, Audio I/O board, trackpad (you will need to remove it from the enclosure.), trackpad cable, and the battery management board (you will need to pull up the protective cover and foam) for any green discoloration, if any is found, proceed to "Corrosion on mainboard" in repair steps.

### Repair Steps
#### Unable to access Apple Diagnostics
If you are unable to access the diagnostics, or it reports no errors, test the laptop with a KNOWN GOOD battery. Battery issues presenting with high fan speed/hanging on boot are very common on A2179 devices.

#### Corrosion found
Replace any corroded components on the system board per visual inspection including the trackpad/trackpad cable.
