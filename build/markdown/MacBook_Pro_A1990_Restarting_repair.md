---
title: "MacBook Pro A1990 Restarting repair"
pageid: 8213
revid: 12059
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1990_Restarting_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1990_Restarting_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=12059"
last_edited: "2025-09-24T13:50:40Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1990"
infobox:
  Device: "MacBook Pro A1990"
  Affects_parts: "TouchBar, Main Logic Board"
  Difficulty: "3. Hard"
  Needs_equipment: "Screwdrivers"
  Type: "Parts Disassembly"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1990 Restarting repair

## Problem Description
MacBook Pro 15” A1990 randomly restarts shortly after boot. Before restarting, you may notice the trackpad freezing for a few seconds, and then macOS triggers a kernel panic.

A panic log shows BridgeOS panic, which drives the Touch Bar.

This issue is commonly caused by a faulty Touch Bar or BridgeOS communication failure, not by macOS, SSD, or user data.
----
![MacBook Pro A1990 Touch Bar (bridgeOS) Panic Log](images/a/a0/A1990-touchbar-panic.png)

## Symptoms
- Mac boots to macOS, but freezes shortly after startup.
- Trackpad stops responding before reboot.
- Device restarts on a loop.
- Touch Bar not working (blank or unresponsive).
- No liquid damage or visible board damage.
- Apple Diagnostics and Disk Utility show no errors.
- Issue persists in Safe Mode and Recovery Mode.

----
![MacBook Pro A1990 Touch Bar FPC Connector Location](images/6/6c/A1990-touchbar-location.png)

## Diagnostic Steps
1. Check Panic Log
1. * Panic log will mention bridgeOS  issues.
1. * This confirms Touch Bar communication error.
1. Visual Inspection
1. * Inspect Touch Bar flex cable and connectors for corrosion or physical damage.
1. * Check for pin damage at Touch Bar connector on logic board.
1. Test Without Touch Bar
1. * Disconnect the Touch Bar flex from the logic board.
1. * Boot macOS and observe behavior.
1. * If restart loop stops, Touch Bar is confirmed faulty.

----

## Solutions
### Option 1: Disconnect Touch Bar (Temporary Fix)
- Disconnect Touch Bar flex from logic board and run Mac without Touch Bar.
- If system boots and stays stable, you’ve isolated the issue.
- Note: Device will run without Touch Bar functionality.

### Option 2: Replace Touch Bar Assembly
- Replace Touch Bar or entire Top Case with a known-good part.
- This resolves BridgeOS crash and restores full functionality.
