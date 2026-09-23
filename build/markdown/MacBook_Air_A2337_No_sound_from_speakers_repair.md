---
title: "MacBook Air A2337 No sound from speakers repair"
pageid: 61
revid: 452
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Air_A2337_No_sound_from_speakers_repair"
history: "https://repair.wiki/index.php?title=MacBook_Air_A2337_No_sound_from_speakers_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=452"
last_edited: "2023-10-29T15:18:02Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Air A2337"
  - "Stubs"
infobox:
  Device: "MacBook Air A2337"
  Affects_parts: "Motherboard"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Air A2337 No sound from speakers repair

## Problem description
Issue with MacBook Air A2337 not playing sound from speakers.![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- No sound from speakers
- Not a software issue

## Solution
### Diagnostic Steps
#### Check SPKRAMP_1V8_RESET_L
You should measure 1.8V, if you measure 0 volts, proceed to the repair steps below.

### Repair Steps
#### No or low SPKRAMP_1V8_RESET_L
- UR900 is most likely the issue.
- Run wire from CR901 pin 2 that has 1.8 volts to pin 1 of CE904 this will force SPKRAMP_1V8_RESET_L high and allow speakers to power up.

  - Note: As of writing I could not find UR900 (SN74AVC4T234) for purchase it is recommended you replace UR900 but this workaround works fine so far assuming UR900 is being told to turn on and SPKRAMP_RESET_L is present.**
