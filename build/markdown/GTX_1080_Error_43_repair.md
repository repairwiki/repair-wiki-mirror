---
title: "GTX 1080 Error 43 repair"
pageid: 676
revid: 1534
kind: repair_guide
source: "https://repair.wiki/w/GTX_1080_Error_43_repair"
history: "https://repair.wiki/index.php?title=GTX_1080_Error_43_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=1534"
last_edited: "2023-12-17T19:11:21Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for GTX 1080"
  - "Repair guides for GTX 1080Ti"
  - "Stubs"
infobox:
  Device: "GTX 1080, GTX 1080Ti"
  Affects_parts: "Whole board"
  Needs_equipment: "multimeter, soldering iron, soldering station, BGA rework station"
  Type: "BGA, Soldering, Software"
  Difficulty: "4. Specialist"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# GTX 1080 Error 43 repair

## Problem description
Error 43 on a GTX 1080, or any NVIDIA graphics card, typically indicates a driver-related issue. This error code is a part of the Device Manager in Windows and suggests that the graphics card has been disabled due to a problem. Usually hardware problem. Here you'll find multiple ways to identify the cause and potentially fix it.
![Error 43 on device manager for GTX 1080 (Figure 1)](images/a/ac/Gtx_1080_error_43.jpg)

## Symptoms
- Error 43 in Device manager
- Display in low resolution
- Sometimes artifacts on the screen

## Solution
### Diagnostic Steps
#### Verify the integrity of the Video Memory VRAM
[More details here](Nvidia_GPU_Memory_Testing_Guide.md). You'll have to run MATS and verify that all the memory chips are in working order. If you get errors on one or more memory chips, proceed to the repair steps below.

#### Check for corrupted BIOS
The easiest way to check if the BIOS is corrupted is by saving a copy of the bios using either [https://www.techpowerup.com/download/nvidia-nvflash/ NVFLASH] or a hardware tool like CH341A or similar BIOS programmers then comparing the saved BIOS with an original BIOS image from [https://www.techpowerup.com/vgabios/ TPU BIOS Collection]

- Download and extract NVFLASH
  - If you have a hardware programmer then connect it to the bios chip and using the software save the BIOS image.
- Use CMD with admin rights in the location of the extracted NVFLASH and run this command *"nvflash64 -b bios.rom"*
- Your saved bios will be named bios.rom.
- Compare the saved file with a file downloaded from TPU. Use [https://www.dwdvb.com/neoprogrammer-new-update-v2-2-0-10/ Neoprogrammer] or [https://ch341aprogrammersoftware.com/ CH341a programmer]
- If the files are different then proceed to repair steps below.

### Repair Steps
#### VRAM issue
If one or more VRAM chips have errors on MATS then this means you have to change them. Beware that changing BGA chips requires professional equipment and experience, if you've never done this before it is best to give it to a service technician.

#### BIOS issue
If the bios is corrupted then you simply need to reflash the original BIOS. Use NVFLASH or a hardware programmer. Sometimes NVFLASH might not want to flash if the card is in that state so it is always best to use a hardware programmer.

#### Neither VRAM or BIOS issue
In cases like this, it is 99% caused by a failing core. This means that the only way to repair the card is to replace the core. Unless you have a core laying around this card is unrepairable at this point.
