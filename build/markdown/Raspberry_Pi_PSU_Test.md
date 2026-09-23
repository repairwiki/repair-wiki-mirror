---
title: "Raspberry Pi PSU Test"
pageid: 944
revid: 2315
kind: explanatory_guide
source: "https://repair.wiki/w/Raspberry_Pi_PSU_Test"
history: "https://repair.wiki/index.php?title=Raspberry_Pi_PSU_Test&action=history"
permalink: "https://repair.wiki/index.php?oldid=2315"
last_edited: "2024-01-13T20:44:34Z"
contributors:
  - "ASRepairs"
  - "HaileyKitty"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for Raspberry Pi"
  - "Stubs"
infobox:
  Device: "Raspberry Pi"
  Type: "Method"
  Difficulty: "1. Easy"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Raspberry Pi PSU Test

To test if a Raspberry Pi is receiving enough power, the `stress` package can be installed:
 sudo apt update && sudo apt install stress
Let the following command run for a minute, then quit it with `ctrl`+`C`:
 watch timeout 1s stress -m 4 --vm-bytes 50
Finally, check if the Pi has received enough power:
 vcgencmd get_throttled
If the above command returns anything other than `throttled=0x0`, the Pi is not receiving enough power. This can be caused by a weak power supply, a bad cable (too long, to thin...), or a faulty Pi.
