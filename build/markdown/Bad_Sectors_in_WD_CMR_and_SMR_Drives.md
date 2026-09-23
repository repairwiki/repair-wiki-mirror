---
title: "Bad Sectors in WD CMR and SMR Drives"
pageid: 5599
revid: 8858
kind: other
source: "https://repair.wiki/w/Bad_Sectors_in_WD_CMR_and_SMR_Drives"
history: "https://repair.wiki/index.php?title=Bad_Sectors_in_WD_CMR_and_SMR_Drives&action=history"
permalink: "https://repair.wiki/index.php?oldid=8858"
last_edited: "2025-07-19T21:02:33Z"
contributors:
  - "Chris"
anonymous_edits: 0
categories:
  - "Missing device page"
  - "Repair guide"
  - "Repair guides for Western Digital CMR and SMR drives"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Bad Sectors in WD CMR and SMR Drives

## Problem description
  - Bad Sectors in WD CMR and SMR Drives**

One of the most common causes of data inaccessibility on hard drives is the presence of bad sectors. As we know, a hard drive stores data as binary (zeros and ones) on a magnetic surface, and a sector is the smallest physical unit of data storage. Think of it as a tiny square on the disk platter where information is stored.

When a sector becomes damaged, special mechanisms built into the drive's firmware attempt to relocate the data and replace the bad sector with a healthy one. This process is called *reallocation*.

However, in many cases, the number of bad sectors is so high, or they are located in such critical areas, that reallocation is no longer possible. In such scenarios, drives may begin to behave abnormally they may become extremely slow or stop granting access to user data.

When that happens, it’s essential to stop all automatic repair mechanisms in order to regain access to the data.

In WD drives, there are two different approaches depending on the drive type.

First part of this article focuses on CMR drives.

## Solution
  - !!! IMPORTANT !!!**

  - DO NOT ATTEMPT THIS PROCEDURE ON SMR DRIVES!**

  - The solution for SMR drives is on the end of this article**

1.)    Separation of the head stack assembly from the PCB to gain access to Kernel mode.

![577x577px](images/6/63/1.JPG)

2.)    Block the Service Area access
![895x895px](images/b/b6/2_SA_access_block.png)
3.)   Power the drive off, remove the isolation and screw the PCB in

4.)   Power the drive on

5.)   In this moment the drive should get ready very fast. You need to start the utility in the Kernel mode
![1422x1422px](images/1/10/3.png)
6.)   Like you can see the ID of the drive is wrong. You need to sent the DIR and module 02 in the HDDs RAM
![677x677px](images/0/09/4.png)
7.)   In the case of CMR drive we can upload those files from the HDD Service Area (SA)
![496x496px](images/8/82/5.png)
![976x976px](images/f/f1/6.png)
8.)   After this the ID of the drive change to SN#XYZ--- At this step you should have an access to the SA and make a backup of it
![701x701px](images/9/9e/7.png)
9.)   Choose or create a new profile and hit OK
![542x542px](images/6/60/8.png)
Here the backup of the SA modules begins
![404x404px](images/7/7a/9.png)
10.)  If you don’t have any issues with the modules you can go to do:
![746x746px](images/5/58/10.png)
![391x391px](images/5/59/11.png)
![460x460px](images/9/9e/12.png)
11.)   Now you can allow the Service Area access and restart the drive
![611x611px](images/c/c0/13.png)
12.)   There is only one step to do, we need to check if the data is encrypted. After restarting the drive go to the Sector Edit (ALT+V) and check sector 0. If you see something like this it means the data is encrypted by the HDD firmware
![808x808px](images/7/7b/14.png)
13.)   Decrypting the data:
![1020x1020px](images/d/d6/15.png)
14.)   When you hit the Autodetect button the software will fine the key in the Service Area
![860x860px](images/1/1e/16.png)
Now you have access to the encrypted data
![760x760px](images/c/c9/17.png)
  - Solution for SMR drives**

  - Why can’t we apply the same methods used for CMR drives to SMR drives?**

Because SMR drives react very poorly to changes in settings and clearing the relocation list. One of the main reasons for this behavior is the Second Level Translator (T2), which is specific to SMR drives. Changing even a single byte requires significant effort from the drive and results in extensive modifications within the T2 translator.

That’s why bad sectors on SMR drives are often accompanied by damage to the T2 translator.

So how can we deal with this problem?

The initial steps will be the same as before:

1.      Head separation

2.      Powering on the drive in Kernel mode and blocking access to the Service Area

3.      Sending the LDR (loader) and module 02 to the drive’s RAM

That means up to step 10.) we proceed according to the previous solution.

11.)   After the modules backup, instead of “Slow slow responding problem” solution in the “Work with service area” drop down menu hit “Edit HDD ID”
![695x695px](images/8/88/18.png)
12.)   Click CFG tab and turn off the relocation
![657x657px](images/b/ba/19.png)
13.)   Go to SMART tab and turn DRM off and click OK
![647x647px](images/0/07/20.png)
14.)   Save changes to the both copies and restart the drive
![346x346px](images/7/71/21.png)
![430x430px](images/7/75/22.png)
15.)   Now we need to clear the Relo-list. Go to Tools  -> Utility extensions -> View and Edit HDD resources or you can use Ctrl+Alt+3
![667x667px](images/7/7a/23.png)
16.)   Find module 32 and read it
![614x614px](images/2/24/24.png)
17.)   Now the **PRO tip** is coming, select the HEX values from the address **0x00A0** to the end of the module hit Ctrl+d and fill that area with 0x0
![1120x1120px](images/a/a9/25.png)
18.)   Now you need to recalculate the checksum
![847x847px](images/2/25/26.png)
19.)   Write back corrected module to the HDD
![991x991px](images/f/ff/27.png)
20.)   Now you can allow SA access and check if the data is accessible
![718x718px](images/b/b9/28.png)
Like you can see the drive has correct ID and you have access to the customer’s data.
![818x818px](images/5/50/29.png)
