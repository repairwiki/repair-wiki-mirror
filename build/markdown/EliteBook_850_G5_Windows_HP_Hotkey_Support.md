---
title: "EliteBook 850 G5 Windows HP Hotkey Support"
pageid: 4280
revid: 10084
kind: repair_guide
source: "https://repair.wiki/w/EliteBook_850_G5_Windows_HP_Hotkey_Support"
history: "https://repair.wiki/index.php?title=EliteBook_850_G5_Windows_HP_Hotkey_Support&action=history"
permalink: "https://repair.wiki/index.php?oldid=10084"
last_edited: "2025-08-06T19:03:03Z"
contributors:
  - "Cheapskate777"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for EliteBook 850 G5"
infobox:
  Device: "EliteBook 850 G5"
  Affects_parts: "Windows OS"
  Needs_equipment: "None"
  Type: "Software"
  Difficulty: "1. Easy"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# EliteBook 850 G5 Windows HP Hotkey Support

## Problem description
Hewlett-Packard automatically pushes a firmware update through the Windows updater that opens blank windows when some function keys are pressed.
## Symptoms
![HP Hotkey Error Window](images/2/2f/Elitebook850g5-hotkey-error.png)
- After pressing the brightness or volume keys, a small blank window appears titled "HP Hotkey Support".

## Solution
Install the correct driver with the link below and disable the bad driver.

### Diagnostic Steps
Press brightness/volume keys in Windows and see if blank window appears.
### Repair Steps
#### Windows 10
1. Download https://ftp.hp.com/pub/softpaq/sp91501-92000/sp91903.exe and install this driver.
1. Press the windows key + R. Type **services.msc** and press enter.
1. Scroll down to "HP Hotkey" and adjust the settings for the two services below by right clicking > start/stop and properties menu.
  1. "HP Hotkey Service" should be running, automatic startup. This is the correct driver.
  1. "HP Hotkey UWP Service" should be stopped and disabled. This is the defective driver.
1. The bad firmware will automatically update occasionally and you will need to disable the bad driver again.
  1. To prevent HP from pushing the bad firmware, you may disable all drivers from updates by following the steps.
  1. Press Win + R then type **gpedit.msc**  then press enter. A new window should pop up.
  1. Navigate to Computer Configuration > Administrative Templates > Windows Components > Windows Update.
  1. On the menu on the right, double click on "Do not include drivers with Windows Updates" and set to enabled.
  1. Note that you will have to keep an eye out for important BIOS/driver updates manually using the HP product page.
