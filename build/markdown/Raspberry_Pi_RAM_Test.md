---
title: "Raspberry Pi RAM Test"
pageid: 945
revid: 2316
kind: explanatory_guide
source: "https://repair.wiki/w/Raspberry_Pi_RAM_Test"
history: "https://repair.wiki/index.php?title=Raspberry_Pi_RAM_Test&action=history"
permalink: "https://repair.wiki/index.php?oldid=2316"
last_edited: "2024-01-13T20:44:55Z"
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
  Type: "Troubleshooting/Diagnostics"
  Difficulty: "1. Easy"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Raspberry Pi RAM Test

To test that the RAM is working correctly, the `memtester` package can be installed:
 sudo apt update && sudo apt install memtester
Check how much RAM is available with the `free` command:
 free
This produces the following output:
                 total        used        free      shared  buff/cache   available
 Mem:          945292       64212      609464         696      271616      824816
 Swap:         102396           0      102396
In the above example, 824MB are available. To test those 824MB two times, run the following command:
 sudo memtester 824M 2

- If the command gets killed by the OOM killer, try testing a smaller amount of RAM.
- To test more than 3GB of RAM, a 64 bit version of Raspberry Pi OS must be used.
- To increase the amount of available RAM, close all other programs. You can also boot the Pi in console mode (`sudo raspi-config`, choose options `1`, `S5`, and `B2`) to test the maximum amount of RAM possible.
