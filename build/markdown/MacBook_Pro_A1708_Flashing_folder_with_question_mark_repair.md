---
title: "MacBook Pro A1708 Flashing folder with question mark repair"
pageid: 2548
revid: 5133
kind: other
source: "https://repair.wiki/w/MacBook_Pro_A1708_Flashing_folder_with_question_mark_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1708_Flashing_folder_with_question_mark_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=5133"
last_edited: "2024-10-27T03:22:56Z"
contributors:
  - "Immortal1857"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1708"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1708 Flashing folder with question mark repair

## Problem description
When turning on the MacBook, it shows a blinking folder with a question mark instead of booting into macOS. Sometimes it will also crash while the lid is closed. This is a cause of the logic board not finding any SSD with a bootable operating system.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- MacBook not booting into macOS
- It showing a blinking folder with a question mark
- It not recognising your internal SSD in internet recovery
- It crashing while the lid is closed (Followed by an error when lid is opened again)

### Diagnostic Steps
- Boot into [https://support.apple.com/guide/mac-help/mchl338cf9a8/mac#mchl69906860 internet recovery] , let the battery drain to ~35% and let the MacBook get warm. Then restart the MacBook a few times until it hopefully boots up successfully. It being plugged in/out might also be a deciding factor, try both options.
  - Sometimes the failing SSD needs these specific conditions to start. Think of it like a failing engine not wanting to start.

- If this worked, make sure to backup **all** of your data to an external drive or to a cloud. Be very sure to not let the MacBook go to sleep mode during this process, every powering on might be the last one it does.
  - If this (and step one of the repair section) didn't work though, your data is very likely lost. A specialist might help recover it, but booting macOS normally will probably be impossible.

### Repair Steps
- Open up the MacBook, unplug the battery and take out the SSD. Clean its connector with isopropyl or an eraser, make sure to get rid of all possible corrosion and then try booting again.

- If that didn't work, a new SSD will be the way to go. I recommend going with a NVME M.2 SSD and the [https://c1.neweggimages.com/productimage/nb300/B8VPD2309220H2AWMD7.jpg corresponding adapter], as a used Apple original one will be just as prone to failure as the old one.
