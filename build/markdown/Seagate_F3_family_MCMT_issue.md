---
title: "Seagate F3 family MCMT issue"
pageid: 4565
revid: 12175
kind: repair_guide
source: "https://repair.wiki/w/Seagate_F3_family_MCMT_issue"
history: "https://repair.wiki/index.php?title=Seagate_F3_family_MCMT_issue&action=history"
permalink: "https://repair.wiki/index.php?oldid=12175"
last_edited: "2025-09-28T20:00:07Z"
contributors:
  - "VCCBoardRepairs"
  - "Chris"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for F3 Family HDDs"
  - "Stubs"
infobox:
  Device: "F3 Family HDDs"
  Affects_parts: "Firmware"
  Needs_equipment: "PC3000"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Seagate F3 family MCMT issue

## Problem description
How to recognize MCMT issue on Seegate Rosewood drives and get access to the data again.

What is the Media Cache Management Table? This is the special table responsible for the media cache 😊

Ok then. What the Media Cache is?

This is a special area located on the edge of the platter where the right/write speed is the highest. It stores the most frequently used/last updated data. It may contain parts of the file system (e.g. parts of the MFT table) and important operating system files. Therefore, it is very important to make copies of the system file 348 (346 in older drives) or module 50 before starting to work with MCMT.

In this article, we will consider the case of a damaged MCMT in the ST5000LM000 drive, although it is the M11 family, in the case of the Rosewood family the procedure is identical.

![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
So how do you recognize a damaged MCMT board?

There are several symptoms in the terminal:

1.)  MCMT corrupted

2.)  SIM Error with 348 in the ID – this is physical damage od the file most likely the file can’t be read

3.)  Update Mask

4.)  Edac Value

5.)  [Scrub Remove]!

6.)  SP Regen Fail
![717x717px](images/5/58/SP_Regen_terminal.png)
7.)  Search IDEDC index

8.)  Stuck LED + BSY status register

9.)  In the Rosewood family DWF issue

## Solution
How to fix the issue and get access to the data?

1. Prepare the ROM
![653x653px](images/a/ab/Unlock.png)
2. Unlock the ROM
![761x761px](images/0/07/Unlock_2.png)
3. Get the terminal access with pressing CRTL + Z
![690x690px](images/2/2c/Unlock_3.png)
4. Now it is the time to make copies of the most important system files, don’t forget save both copies of those files, it’s very important:

- 3x1B – P list
- 3x28 – translator
- 3x35 – Non Resident G-List
- 3x93 – SMP flags
- 3x348 – MCMT
![710x710px](images/7/74/Files_save_1.png)

![705x705px](images/3/34/Files_save_2.png)
5. Now we need to compere both copies of the file 348.
![742x742px](images/6/6a/Comparing_the_files.png)
![895x895px](images/0/0c/Comparing_the_files_2.png)
6. It is the time for clear the MCMT by using /CU10 command in the terminal. This command is going to clear the MCMT but we have it’s copies so we can work with them later.
![898x898px](images/2/21/CU10.png)
7. Repower the drive and restart the utility if you need

8. Now the drive is stabile and we can make a backup of the HDD resources
![888x888px](images/5/5c/Boot.png)
9. In ideal conditions everything should be working and you could proceed to create a task in Data Extractor. But usually drives with corrupted MCMT have a lot of bad sectors so it is a good idea to stop their relocation. We do this by editing the system file 93
![Set the flags like on the picture below and click OK](images/9/93/93_edit_1.png)
![875x875px](images/6/6a/93_edit_2.png)
10. This file needs to be write in the ATA indirect mode (Seagate Rosewood family)
![871x871px](images/9/9a/Indirect_mode.png)
![If you have problems with writing this file to the surface I have a small pro tip for you.[[File:Pro tip.png|center|thumb|886x886px|You can write this file as a module 2A using ATA direct mode 😊\]\]](images/8/80/Indirect_mode_2.png)
11. Now the drive is ready for the data recovery process but the MCMT is missing and we don’t have the access to the Media Cache where for example part of the MFT table might be located. We need to fix that issue. Lets open our saved copies of the file 348 and use the MCMT \ Edit and MCMT \ Parser options
![901x901px](images/0/0b/Mcmt_edit1.png)
12. Here we need to fill the “DirtySegmentCount” with 0 and check all the option below that and click OK
![406x406px](images/a/ab/Mcmt_edit2.png)
13. After editing the file we need to fix the check sum
![787x787px](images/7/75/Check_sum_1.png)
![Check sum 2.png](images/9/96/Check_sum_2.png)
14. We look for a place in the file where there are 0000, we change the byte order and check the checksum again
![805x805px](images/1/1c/Check_sum_3.png)
15. We can save the prepared file as module 50 on the drive, but this solution can sometimes be unstable. The best option is to send this file to RAM and then create a task in Data extractor
![829x829px](images/f/fa/Ram_1.png)
![845x845px](images/7/7f/Ram_2.png)
16. Now we can check if we have access to the data

![981x981px](images/0/04/Sector_edit.png)
![435x435px](images/3/31/Sector_edit_1.png)
![623x623px](images/a/a2/Sector_edit_2.png)

Now we can go to Data Extractor and create a new task. It would be a good idea to create a scenario so that in the event of a HDD reset, DE itself sends a handshake and sends MCMT to RAM, but this is material for another long article. I hope I managed to explain at least a little what it is and how to remove errors related to MCMT
