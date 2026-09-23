---
title: "Nintendo Switch Overheating And Joycon Issues Repair"
pageid: 927
revid: 2283
kind: repair_guide
source: "https://repair.wiki/w/Nintendo_Switch_Overheating_And_Joycon_Issues_Repair"
history: "https://repair.wiki/index.php?title=Nintendo_Switch_Overheating_And_Joycon_Issues_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=2283"
last_edited: "2024-01-13T20:28:42Z"
contributors:
  - "ASRepairs"
  - "HaileyKitty"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Nintendo Switch"
  - "Stubs"
infobox:
  Device: "Nintendo Switch"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "lab Bench PSU"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Nintendo Switch Overheating And Joycon Issues Repair

## Problem description
The Nintendo Switch has a complex power system for the cooling system, one which shares its resources with power feeding the Joy-con rails to charge the joy-cons.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Overheating
- Joy-con issues

## Solution
If the console shows warning signs saying it is getting too hot, and eventually shutting down, or if you are experiencing issues with joy-cons connecting to the system and charging, you probably have a problem with the fan circuit.

### Diagnostic Steps
No fan spin and/or no joy-con charging is typically caused by a small mosfet located just above M92T36.

Occasionally this mosfet can fail open, meaning 3v is not allowed to pass through to power the circuit. Other times the mosfet can be perfectly fine, and the issue will be down to either a faulty fan, faulty joy-con rails or corrosion around one of the components on that line.

### Repair Steps
The easiest solution is to very briefly inject 3v into the fan circuit. Simply tap the 3v line 2 or 3 times for a brief second or 2, and the mosfet will usually magically come back to life.

I've personally known this to be a long lasting solution with zero warranty returns in the past 12 months using this method.

Ensure that no joy-cons are connected, but you will want to make sure the console is turned on during this process.

Sometimes by leaving the console on it will fire up the fan immediately because the CPU will be warm enough to need it, which will confirm success. If the voltage injection method fails, replacing the mosfet is the only option.
