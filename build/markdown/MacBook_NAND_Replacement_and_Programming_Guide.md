---
title: "MacBook NAND Replacement and Programming Guide"
pageid: 9712
revid: 14064
kind: explanatory_guide
source: "https://repair.wiki/w/MacBook_NAND_Replacement_and_Programming_Guide"
history: "https://repair.wiki/index.php?title=MacBook_NAND_Replacement_and_Programming_Guide&action=history"
permalink: "https://repair.wiki/index.php?oldid=14064"
last_edited: "2026-02-22T02:56:27Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for MacBook Pro A1990"
  - "Explanatory guides for MacBook Pro A2141"
infobox:
  Type: "Soldering"
  Device: "MacBook Pro A1990, MacBook Pro A2141"
  Difficulty: "4. Specialist"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook NAND Replacement and Programming Guide

MacBook storage upgrade or NAND failure requires replacement of onboard NAND flash chips. Since Apple SSD storage is directly soldered to the logic board, new NAND chips must be:

- Correctly programmed
- Properly mapped
- Installed in correct positions
- Restored via DFU after installation

Improper programming or incorrect NAND placement will result in:

- No boot
- Restore failure
- Incorrect storage detection

----

## Requirements
- JC Programmer (with JCID Assistant software)
- Compatible blank NAND chips
- Hot air station
- Microscope
- Donor Mac (for DFU restore)
- USB-C cable

----

## Important Notes Before Starting
- NAND positions are board-specific (e.g., U9200, U9100, etc.)
- Chips must be installed in the exact mapped positions
- Always mark chips after programming
- Storage size selection must match desired final capacity

----

# Procedure
----

## Step 1 – Connect Programmer
1. Connect JC Programmer to PC
1. Open JCID Assistant software![Mac-nand-1.png](images/9/98/Mac-nand-1.png)

----

## Step 2 – Select Mac Series
1. From the left-side dropdown menu
1. Select the Mac series you are programming for![Mac-nand-2.png](images/9/90/Mac-nand-2.png)

----

## Step 3 – Select Specific Model
Example:

For this guide, select:<blockquote>MacBook Pro 2019 – A2141</blockquote>Always ensure:

- Model matches exactly![Mac-nand-3.png](images/c/cc/Mac-nand-3.png)

----

## Step 4 – Select Storage Capacity
Choose the storage size you want to program:

- 256GB
- 512GB
- 1TB
- 2TB (if supported)

Example:

- If upgrading to 1TB, select 1TB
- If original device was 512GB, select 512GB

Capacity must match chip configuration.
![Mac-nand-4.png](images/3/39/Mac-nand-4.png)
----

## Step 5 – Program NAND Chips
1. Insert NAND chip into programmer
1. Click Write JC Data
1. Wait for programming to complete
1. Remove chip

⚠️ After programming each chip:

- Mark it clearly (e.g., U9200, U9100, etc.)
- Use a marker or fine-tip Sharpie
- This prevents position mix-up during soldering

Repeat process for all NAND chips.
![Mac-nand-5.png](images/0/01/Mac-nand-5.png)
----

## Step 6 – Install NAND Chips
1. Remove old NAND chips from logic board
1. Clean pads thoroughly
1. Reball new NAND chips (if required)
1. Install each chip in correct labeled position
1. Inspect solder joints under microscope

⚠️ Incorrect placement = no boot or restore failure.
----

## Step 7 – DFU Restore
After soldering:

1. Use a second working Mac
1. Connect target Mac via USB-C
1. Enter DFU mode
1. Open Apple Configurator
1. Perform Restore

⚠️ Restore is required to initialize new storage.
----

## Step 8 – Verification
After restore completes:

1. Boot MacBook
1. Complete setup
1. Go to:
1. * About This Mac → Storage
1. Confirm upgraded storage capacity

Example:

- 512GB → now shows 1TB

----

# Expected Result
- Mac boots normally
- Storage capacity reflects selected size
- System stable
- No SSD-related errors

-
