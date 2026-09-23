---
title: "75\" Class Q7F QLED 4K TV (QN75Q7FAMFXZA) No Power"
pageid: 4841
revid: 7960
kind: other
source: "https://repair.wiki/w/75%22_Class_Q7F_QLED_4K_TV_(QN75Q7FAMFXZA)_No_Power"
history: "https://repair.wiki/index.php?title=75%22_Class_Q7F_QLED_4K_TV_(QN75Q7FAMFXZA)_No_Power&action=history"
permalink: "https://repair.wiki/index.php?oldid=7960"
last_edited: "2025-06-22T22:53:43Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for 75\" Class Q7F QLED 4K TV (QN75Q7FAMFXZA)"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# 75" Class Q7F QLED 4K TV (QN75Q7FAMFXZA) No Power

## Problem description
The TV does not turn on.

The most common issue with this TV is a power supply problem.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- The TV does not turn on
- The Standby LED is not present

## Warning!!!
Usualy TVs have exposed power supplies and the Capacitors on them can be charged even if the TV is unplugged from the wall.

Only touch the Power supply by the edges of the PCB and it is recommended for you to use gloves.

If you touch the wrong place you may be shocked and you can get seriously hurt.

Be specially careful not to touch these capacitors.

![Capacitors that you need to be careful](images/7/7c/Capacitors_that_you_need_to_be_careful.png)

### Disassembling the TV
In order to diagnose the problem with the TV we gonna have to open it.

This TV and and many samsung TVs are screw less so you need a special tool to open it (**BN81-14946B)**

This tool can be found on many websites on online.
![**Special tool used to open samsung TVs**](images/c/c0/BN81-14946B.png)
The are 2 holes on the bottow side of the tv insert the tool like in the image bellow.
![Place to insert tool](images/c/cc/Place_to_insert_tool.png)
You will see that the plastic cover will pop then start going around the TV like this.
![Going around the TV](images/2/22/Next_step_.png)

After going around all the plastic it will come loose simply lift it and put it a side.

### Diagnostic Steps
The first step is to understand if the problem is on the main board or the Power supply, to do this we will disconect the cable that goes from the PSU to the main board.
![Cable to disconnect](images/5/5a/Cable_to_disconnect.png)
After disconnecting this cable plug the tv into the wall if the backlight of the TV turns on it means that issue is on the main board, if the backlight does not turn it means there is an issue with the PSU.

Remove the PSU from the TV.

The first thing we gonna check is if the Fuse is good to do this put your multimeter in continuity mode and measure it if the fuse is good the multimeter will beep.
![Fuse](images/1/1d/Fuse.png)
If the fuse is good (most likely will be) the next step is to inpect the solder joints of these components this is the number one fault on this model.

![Component to Check](images/2/2b/Component_to_Check.png)

Use a microscope to inspect the solder joints of every pin it is common to have cracks like the image bellow.
![Craked Solder joint](images/c/cd/Craked_Solder_joint.png)

### Repair Steps
If the problem is on the power supply you can choose to repair or to simply replace it.

To repair the broken solder join:

Start by applying flux and low melt solder with your soldering iron then use solder with to clean the solder.

After cleaning the old solder clean the PCB with a q-tip and isopropyl alcohol.

Apply fresh flux and use a good solder to solder the pin to the PCB.

This process is recomended for every pin of these components not just the one with the broken connection.

## Final Testing
After reparing the PSU assemble the TV again expect for the plastic cover.

Connect the TV to the wall and see if it will turn on, if every thing looks fine you can them install the plastic cover again.
