---
title: "Panasonic AG-VBR89G battery family - How to ID issues and revive over-drained batteries"
pageid: 9158
revid: 13948
kind: explanatory_guide
source: "https://repair.wiki/w/Panasonic_AG-VBR89G_battery_family_-_How_to_ID_issues_and_revive_over-drained_batteries"
history: "https://repair.wiki/index.php?title=Panasonic_AG-VBR89G_battery_family_-_How_to_ID_issues_and_revive_over-drained_batteries&action=history"
permalink: "https://repair.wiki/index.php?oldid=13948"
last_edited: "2026-02-14T09:28:32Z"
contributors:
  - "VCCBoardRepairs"
  - "RoseHunter"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for Panasonic"
  - "Missing device page"
infobox:
  Difficulty: "1. Easy"
  Device: "Panasonic"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Panasonic AG-VBR89G battery family - How to ID issues and revive over-drained batteries

### A brief discussion about the Panasonic AG-VBR battery family.
![Photo of the Dead Batteries](images/9/9b/IMG_20220727_182328~2.jpg)
The AG-VBR battery is widely supported across Panasonic’s professional video lineup, including:

- Panasonic AG-DVX200 (and variants: PJ, PB, PX, EJ, EN, ED)
- Panasonic AJ-PX270 / AJ-PX230 / AJ-PX298 (MC)
- Panasonic AG-CX350
- Panasonic AU-EVA1
- Panasonic AJ-UX90 / AJ-UX180

### A brief background of the situation I found myself in:
I had bought a used Panasonic AG-UX180 Camera that came with several batteries. The issue was that most of the batteries were dead, and refusing to come back to life on the charger, despite leaving them sit overnight. Some of the batteries did however work fine on the charger, so I surmised the issue was likely with the various AG-VBR batteries.

### Troubleshooting Steps:
Due to this situation, I bought a couple off-brand Kastar batteries off of Amazon. They worked with the Panasonic AG UX 180 just fine, but when I went to charge them, to my dismay, they didn't charge on the OEM Panasonic charger (Panasonic AG-BRD50). They showed solid orange lights where my OEM one blinks when it sits on the charger.
![Panasonic Battery Charger for AG-VBR Batteries](images/1/15/PAN-AGBRD50Charger.jpg)
- I tried a bit to see if there was a way to charge the batteries from the camera itself to no avail.

- I tried to connect the batteries to the charger both before the power was plugged in and this also failed.

- I tried to put just the 1 on and found it to blink.

I then put on the OEM battery to verify the same blink pattern. This seemed to be a sign that it was working at that moment, so I allowed them to charge for a few hours before testing to see if they would work.

When I pressed the on-battery indicator button, the light on the battery that was giving me issues was blinking blue at the 0% mark. So I threw them on again that night and got some charge on 1 of the batteries. The next day I went on and put them both on the charger 1 at a time and found that once I hit the battery level test button they both began to blink on the charger so this was 1 way I was able to get them to initialize a revival.

I found it difficult to locate a manual for the Panasonic AG-BRD50 charger besides some minimal information here: https://www.manualslib.com/manual/1543049/Panasonic-Ag-Cx350.html?page=17&term=brd50&selected=4#manual

This is unfortunate, as I could not understand the differences with the indicator lights (solid vs 1 sec interval blink)

Following the above troubleshooting, I found no noticeable difference in charge from the prior night. This leads me to believe:

- The batteries aren't taking a charge
- Blinking does not mean they are charging
- There may be some incompatibility with these batteries and this charger.

The next thing I tried was to try and use my multimeter to test the state of the batteries. Some of them I found were exhibiting signs of undervoltage and even reverse polarity.
![Testing dead Panasonic AG-VBR Battery](images/d/dd/MultimeterTesting.png)

In addition to the above testing, I ended up opening the pack, Testing each cell and sure enough 1 was completely dead/with the polarity reversed. Inside, there were 4 (18650) Lithium cells inside. Wired up ++ -- 2 series; 2 parallel with nickel strips, a temperature sensor and a control/BMS board.
![Opened Panasonic AG-VBR Battery](images/7/74/PanasonicAGVBROpenedup.png)

The batteries all have a button on them that when pressed lights LEDs to indicate charge. I suspect some "smart" component had drained the batteries from the inside over a long period of non-use. I was planning to try and replace the cells in this pack, but I mangled the casing quite a bit. I will post a link to a 3D printable replacement housing if I come across one.

My final step was to try and see if I could buy a different charger that might work to recharge the batteries. I suspected some sort of design flaw/feature that the charger might have is a refusal to charger batteries that exhibit certain characteristics such as undervoltage, Reverse polarity, overheating, etc.

So I ended up buying a Kastar brand charger that was able to charge the batteries that were completely dead. I bought it for $6 on ebay, so it was well worth the price. https://www.ebay.com/itm/254196788483?var=553569162934
![Kastar Brand Charger](images/7/7f/Kastar.png)

###### To Summarize:
It seems to charge any battery I put on it, at a slower rate than the OEM charger, but with far less prejudice about the state of the battery. So the dead OEM batteries were successfully revived by the Kastar brand cheap chinesium charger. OEM loses this battle. Hack the Planet.
