---
title: "Asus GTX 1060 6GB Expedition. Please power down and connect the PCIE power cable(s) for this graphics card"
pageid: 2329
revid: 4911
kind: other
source: "https://repair.wiki/w/Asus_GTX_1060_6GB_Expedition._Please_power_down_and_connect_the_PCIE_power_cable(s)_for_this_graphics_card"
history: "https://repair.wiki/index.php?title=Asus_GTX_1060_6GB_Expedition._Please_power_down_and_connect_the_PCIE_power_cable(s)_for_this_graphics_card&action=history"
permalink: "https://repair.wiki/index.php?oldid=4911"
last_edited: "2024-09-21T23:13:30Z"
contributors:
  - "Galkinvv"
  - "Kibillcat"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for GTX 1060"
  - "Repair guides for GTX 1070"
  - "Repair guides for GTX 1070Ti"
  - "Repair guides for GTX 1080"
  - "Repair guides for GTX 1080Ti"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Asus GTX 1060 6GB Expedition. Please power down and connect the PCIE power cable(s) for this graphics card

![Figure 1: Broken off resistor](images/3/33/20240827_190747.jpg)

## Problem description
After installing graphics card to system suddenly gives "Please power down and connect the PCIE power cable(s) for this graphics card" error even though the cable is connected.

This guide will give detailed instructions on personal experience and will try to give directions, hints for users who have same error, but different card, cause and etc.

## Possible causes
- Moving GPU to new system.
- Trying to cable manage and hide extra 2pin connector inside GPU casing.
- Cleaning, repasting GPU die.
- Broken off SMD component.
- Failed component(s) broke line from 6pin sense pin to power management IC.

## Symptoms
## Solution for this specific issue
![Figure 2: Broken off resistor. Zoomed in.](images/1/19/20240827_190717.jpg)
This solution is specific to my issue. Same error, but causes could be different. I received this error during MB+CPU+RAM upgrade and then trying to hide 2pin cable for better looks in GPU cut out next to 6pin connector. At that moment I didint knew that I had accidentally broken of resistor and made conclusion after repairs. Steps taken:

1. Inspected power cables, tested on different system - it is indeed a GPU issue.
1. Inspected board. Noticed missing resistor. According to boardview its R1079. See image "Figure 1". Zoomed in version "Figure 2". It is very easily missable and hard to notice that it was broken off.
1. Getting resistor value from boardview. Its 0 ohm resistor. So just bridging contacts with solder. See "Figure 3".
![Figure 3: Bridged contacts, 6pin connector PCB side](images/d/d6/20240831_191407.jpg)

### Diagnostic Steps / Repair steps
1. The basics. Power cables.
  1. Make sure 6pin connector is plugged all the way in to the GPU side.
  1. Make sure the PSU side for PCIe power connector plugged all the way in if its modular.
  1. Try with different PCIe cable. Make sure that the cable is from used PSU if modular. Otherwise huge risk of burning down GPU. (If possible)
  1. Try in different system. (If possible)
  1. Measure with multimeter if 12v coming from PSU and when connected to GPU. (if not possible to do 1.3 and 1.4 steps. To eliminate faulty PSU)
1. Visual inspection.
  1. Carefully inspect 6pin side board on both sides for broken off, burnt components or torn traces.
  1. Take your time. Without microscope it takes great eyesight and focus to notice broken off component or other anomalies.
  1. * One option is to look for pictures online and compare to your card. However it will be challenging to find high quality picture of PCB, especially top side.
1. Searching for schematics/boardview.
  1. Try to search with model name. If no success - via PCB model, it should be writen somewhere.
  1. Same PCB could be used for different model. In this case Asus GTX 1060 6GB Expedition PCB is also used for Asus GTX 1060 6GB Dual.
  1. * You will not always find it. In this case try to find similar model schematics/boardview to give general idea what to look for. It will also be harder to determine broken component value. (explained in next step)
1. Looking for broken connection.
1. * Generally speaking, GPU has to know in some way if 6pin is connected or not, something has to report it. Thats why 6pin connector on GPU has "sense" pin which is connected to some power management IC through various components on board to report to GPU that 6pin is connected and let it to fully power up. And if connection is broken, from sense pin to power management IC it doesnt see connected 6pin connector and gives previously mentioned error. Usually its "GPIO LOW_PERF" signal line. (This explanation is overly simplified and couldnt think of better way phrasing it)
1. * Then broken connection can be found on the board by using multimeter "beep mode" with one probe fixed on a known place (starting with sense pin of a power connector) and the other where it should connect looking via schematics. Going through different components - test accordingly if theyre are good. And if you found missing, broken - thats most likely the cause. If its burnt - I think it needs more investigation to figure out what caused it, because it might burn again or not.
1. * If dont have schematics, then you will need to look to similar as a reference.![Asus GTX 1060 6GB Bottom PCB view](images/c/cd/20240831_190654.jpg)
![Asus GTX 1060 6GB Top PCB view](images/8/89/20240831_191127.jpg)

### Additional info
Small addition to the "lack of schematics" case: the message about PCIe power connector has common mechanics in ALL nvidia GPUs for ~10 years.

So the schematics for slightly similar model can be used for reference. Such schematics will give the idea which elements are used to sense power connector presence and report to the GPU via logic low/high of "GPIO LOW_PERF" signal line. Then such elements can be found on the board by using multimeter "beep mode" with one probe fixed on a known place (starting with sense pin of a power connector) and the other scanning the board for connected elements. This way, the area of mentioned above elements can be found and precisely inspected for damage.

Original post that made me create this guide: [https://www.reddit.com/r/GPURepair/comments/1f2qv0t/fixed_asus_gtx_1060_6gb_expedition_please_power/ [Fixed] Asus GTX 1060 6GB Expedition. Please power down and connect the PCIE power cable(s) for this graphics card]

Repair steps are according to "Diagnostics Steps"

1.
