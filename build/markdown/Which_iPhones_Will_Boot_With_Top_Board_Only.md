---
title: "Which iPhones Will Boot With Top Board Only"
pageid: 539
revid: 3588
kind: explanatory_guide
source: "https://repair.wiki/w/Which_iPhones_Will_Boot_With_Top_Board_Only"
history: "https://repair.wiki/index.php?title=Which_iPhones_Will_Boot_With_Top_Board_Only&action=history"
permalink: "https://repair.wiki/index.php?oldid=3588"
last_edited: "2024-03-05T21:36:31Z"
contributors:
  - "VCCBoardRepairs"
anonymous_edits: 1
categories:
  - "Explanatory guide"
  - "Explanatory guides for IPhone 11"
  - "Explanatory guides for IPhone 11 Pro"
  - "Explanatory guides for IPhone 11 Pro Max"
  - "Explanatory guides for IPhone 12"
  - "Explanatory guides for IPhone 12 Mini"
  - "Explanatory guides for IPhone 12 Pro"
  - "Explanatory guides for IPhone 12 Pro Max"
  - "Explanatory guides for IPhone 13"
  - "Explanatory guides for IPhone 13 Mini"
  - "Explanatory guides for IPhone 13 Pro"
  - "Explanatory guides for IPhone 13 Pro Max"
  - "Explanatory guides for IPhone 14"
  - "Explanatory guides for IPhone 14 Plus"
  - "Explanatory guides for IPhone 14 Pro"
  - "Explanatory guides for IPhone 14 Pro Max"
  - "Explanatory guides for IPhone 15"
  - "Explanatory guides for IPhone 15 Plus"
  - "Explanatory guides for IPhone 15 Pro"
  - "Explanatory guides for IPhone 15 Pro Max"
  - "Explanatory guides for IPhone X"
  - "Explanatory guides for IPhone XS"
  - "Explanatory guides for IPhone XS Max"
infobox:
  Device: "IPhone X, IPhone XS, IPhone XS Max, IPhone 11, IPhone 11 Pro, IPhone 11 Pro Max, IPhone 12, IPhone 12 Mini, IPhone 12 Pro, IPhone 12 Pro Max, IPhone 13, IPhone 13 Mini, IPhone 13 Pro, IPhone 13 Pro Max, IPhone 14, IPhone 14 Plus, IPhone 14 Pro, IPhone 14 Pro Max, IPhone 15, IPhone 15 Plus, IPhone 15 Pro, IPhone 15 Pro Max"
  Type: "Troubleshooting/Diagnostics"
  Difficulty: "1. Easy"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Which iPhones Will Boot With Top Board Only

## Summary
When troubleshooting a board issue on a 2 layer sandwich board, sometimes it's a good idea to isolate the board to the bare minimum. ![Example of an iPhone 15 sandwich board separated into its 2 layers](images/a/a9/IPhone_15_Sandwich.jpg)That includes, splitting the sandwich & test with the top board only.

When testing with top board only or with a non-original bottom board, you may get a white screen that says "Swipe To Recover". This just means it needs to "reconfigure itself" with the new NFC chip it has detected. All you have to do is type in the correct pin code twice & let it do it things. It will have a loading bard with a "attempting data recovery" message.

If it goes back to the "Swipe To Recover" message, then it means the pin code was incorrect or the phone restarted.

When in doubt, test the top board with a known good bottom board in a socket jig tool, like a Qianli iSocket.

## Top Board Only Useful Info
Below is a list of each sandwich model & what happens when you test with top board only

| Top Board Only Sandwich Boards | Will boot? | Touch? | Restart Issues? | Temp Warning Issue? | Notes |
| --- | --- | --- | --- | --- | --- |
| iPhone X (Intel) | No | No | N/A | N/A |  # Top Board Only will boot to DFU Mode. You can flash & retain user data on 3u Tools to get it to boot. # Or you can bypass dfu mode with top board only by running a jumper from pin S41 to S48 # Requires Charging Port to prevent top board only from restarting (Mic1) |
| iPhone X (Qualcomm) | Yes | No | No | No |  # Must use Socket Jig to get touch working # Requires Charging Port to prevent top board only from restarting (Prs0/Mic1) |
| iPhone XS, XS Max | Yes | No | No | No |  # Must use Socket Jig to get touch working # Requires Charging Port to prevent top board only from restarting (Prs0/Mic1) |
| iPhone 11 | Yes | Yes | Yes | No |  # Since mic 2 connects to the main board via the sandwich, it requires the bottom board to avoid 3 min restarts. # Requires the power button flex connected # Requires Charging Port to prevent top board only from restarting (Prs0/Mic1) |
| iPhone 11 Pro, 11 Pro Max | Yes | Yes | No | No |  # Can get data with top board only. Just make sure to plug in a power button flex (Mic2) and charging port flex (Prs0/Mic1) |
| iPhone 12, 12 Pro, 12 Mini | Yes | Yes | No | No |  # Can get data with top board only. Just make sure to plug in a charging port flex (Prs0/Mic1) # If you want brightness to work, plug in the ear speaker flex. If ALS sensor is not detected, screen will stay dim |
| iPhone 12 Pro Max | Yes | Yes | No | Yes |  # With top board only, the phone will boot to a false positive overheating temp warning, even if it's cold. # You can bypass the temp warning by running a 10k Ohm resistor to ground on these 2 lines: a. Pin 487 - NTC_RADIO_BB_SE b. Pin 489 - NTC_RADIO_PA_SE # You can also just plug in a known good bottom board using an iSocket jig to get data # Make sure to plug in a charging port flex (Prs0/Mic1) to prevent 3 min restart # If you want brightness to work, plug in the ear speaker flex. If ALS sensor is not detected, screen will stay dim |
| iPhone 13 Mini | Yes | Yes | Yes | No |  # This model requires the bottom board to prevent 3 min restart (0x400) # The issue is, the top board must communicate with the gyroscope in order to function correctly and not restart every 3 minutes. Rebuilding pads 207, 208, 502, 503, 504, 527, 528 is all that is needed from the bottom board. # You can also just plug in a known good bottom board using an iSocket jig to get data # Requires proximity flex to prevent board only from restarting (0x1000) # Requires charging port flex to prevent board from restarting (0x800) |
| iPhone 13, 13 Pro, 13 Pro Max | Yes | Yes | No | No |  # You can get data with just top board only. # Requires proximity flex to prevent board only from restarting (0x1000) # Requires charging port flex to prevent board from restarting (0x800) |
| iPhone 14, 14 Plus | No | N/A | N/A | N/A |  # Requires both layers connected for the board to boot |
| iPhone 14 Pro, 14 Pro Max | Yes | Yes | Yes | No |  # This model requires the bottom board to prevent 3 min restart. # Unknown what is needed from the bottom board to prevent the 3 min restart. (0x20000) # You can also just plug in a known good bottom board using an iSocket jig to get data # Requires proximity flex to prevent board only from restarting (0x80000 ) # Requires charging port flex to prevent board from restarting (0x40000 ) # Requires the power button flex to prevent board from restarting (0x10000) |
| iPhone 15, 15 Plus | No | N/A | N/A | N/A |  # Requires both layers connected for the board to boot |
| iPhone 15 Pro, 15 Pro Max | Yes | Yes | Yes | No | TBD... |
