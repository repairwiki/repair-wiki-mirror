---
title: "A1278 MacBook Pro won't recognize HDD or SSD when it has macOS installed"
pageid: 2531
revid: 5115
kind: other
source: "https://repair.wiki/w/A1278_MacBook_Pro_won't_recognize_HDD_or_SSD_when_it_has_macOS_installed"
history: "https://repair.wiki/index.php?title=A1278_MacBook_Pro_won't_recognize_HDD_or_SSD_when_it_has_macOS_installed&action=history"
permalink: "https://repair.wiki/index.php?oldid=5115"
last_edited: "2024-10-24T09:45:16Z"
contributors:
  - "XTA"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1278"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# A1278 MacBook Pro won't recognize HDD or SSD when it has macOS installed

## Problem description
Device won't recognize any SSD or HDD with macOS installed, including inside disk utility in the macOS installer. The device will however recognize a drive without macOS installed just fine.

![U6100 - EPROM location on a 820-3115](images/9/9e/12.png)

## Symptoms
- Drives with macOS do not show up in the boot select menu or disk utility however drives without macOS installed (e.g. a windows drive) will show up in the boot select menu and will show up in disk utility.
- Normally but not all the time, this shows up with other issues such as random kernel panics or very slow loading times when attempting to boot into an external macOS installer drive.

## Solution
This is almost always going to be down to a bad / corrupt EFI which is why this issue normally shows up with random kernel panics and the device booting into the macOS installer extremely slow or often hanging on the loading bar.

### Diagnostic Steps
Most of the time this issue will become randomly apparent by your device no longer being able to boot into macOS, these devices also do have other issues with the HDD not being detected so first you must ensure that you are facing the issue of it not detecting drives with macOS installed instead of the device just not detecting any drive at all.

Another way to ensure this is your issue is by booting into a USB with a OpenCore Legacy Patcher EFI written to it (You will need another MacBook Pro to do this), your HDD or SSD will be detected in OpenCore Patcher's EFI if this is the issue you are facing and you can sometimes use this as a work around if you don't have other issues presenting themselves such as random kernel panics or the device just shutting itself off randomly. However it is best to have this issue addressed.
### Repair Steps
On the repair angle you have 3 options.

The first option is to opt for removing the EPROM from another same model logic board and just swapping it, this is the easiest by far.

The 2nd option is to flash a dump of another EFI from another MacBook Pro onto your EPROM (An EFI dump can be found online easily)

The 3rd option is to take the EPROM off another board, flash it with an EFI dump (if needed, I will explain) and change the serial number to match your board's actual serial number and then solder it back on. (Most time consuming, best option)

So a quick run down, the drawback of the first option is 2 things, first your serial number won't match which is okay if you A) don't care or B) aren't fixing this for a customer that will complain about it and the 2nd issue is outside of a repair shop with a bin full of donor boards, this is harder because you need an EXACT match, if you are doing a Early 2011 board, you need an EPROM from an Early 2011 board you can't use a Late 2011 EPROM or a Mid 2012 EPROM, It must be an exact match otherwise you will face issues ranging from random kernel panics to won't boot at all, This is because every board is slightly different and over the different years, different CPU's were used therefore if you put a 2011 EPROM on a 2012, it won't boot. In the case of using an Early on a Late, at least on the 2011's in my experience it causes kernel panics. What I am saying here is, you need a matching donor board which can be hard to locate.

The issue with the 2nd option while yes you could make the serial number match and it does allow you to get out of soldering using a clip on a CH341A (Which I don't recommend anyways), you are reflashing to a possibly failing EPROM, it may not let you reflash it and even if it does, it may corrupt or fail again, it could also work just fine so if it's your own device, have at it! but in the case of repairing a board to be sold or returned to a customer, option 3 is the way to go.

The best option here is number 3, take an EPROM off a donor board, this time it doesn't have to be a matching donor board because you can just flash it with the matching firmware yourself. Grab the matching EFI, put it in a hex editor, search the for the serial number (09-10 is going to start with W8, 2011 is going to start with C02 and 2012 is going to start with C1M) and write over the EFI's serial number with the correct one! This is going to A) Have a better EPROM with a matching EFI on the board AND have it match serial numbers so you don't have a board that's confused with a different serial number in About This Mac and on the bottom case and logic board serial number sticker.

So we will assume you are going with option 3 here.

  - Step 1. Remove donor EPROM and place it in or solder it into your EPROM Programmer**

U6100 is the EPPROM location, right at the top of the board by the fan. Apply flux and tin the legs with leaded solder, using hot air remove the IC (I keep my 861DW at 60 airspeed at 350°c when removing EPROM's), Now either solder it onto the breakout board of your EPROM programmer or place it in your EPROM programmers SOIC8 attachment.

  - Step 2. Obtain your new EFI dump and change the serial number**

Find a dump of an exact match EFI or dump an exact models EFI if you have one, so Late 2011, you need a Late 2011 dump and so on and so fourth, You can skip this and just dump the EFI on the EPROM if it matches the board it's going to, grab the dump and put it in a hex editor such as HxD and search for the serial number, If it's a 08 - 10 dump it's probably going to start with W8, if it's a 2011 dump, it's going to start with C02 and if it's a 2012 dump it's going to start with C1M on A1278 boards. All you need to do is edit it by typing over it with the correct serial number and save it as a bin file with a new name.

  - Step 3. Flash the new EFI**

I can't give you exact instructions here as it changes depending on the software your programmer uses, in most cases it's going to be, read, erase and program (select the new EFI you just saved) and verify. Once everything checks out done!

  - Step 4. Solder the EPROM to your logic board**

Follow the same instructions of removing the EPROM from a donor board on your main board, once removed, wick the pads clean and apply flux and tin the pads and using hot air, flow the new EPROM down to the board, remember pin 1 (the pin that has the circle indent on top of the IC) faces to the top left of the board.

And done! Allow the board to cool down and reassemble the machine, it should now detect macOS drives and boot right up without any issues! :)
