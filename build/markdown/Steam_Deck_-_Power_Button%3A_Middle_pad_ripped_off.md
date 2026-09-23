---
title: "Steam Deck - Power Button: Middle pad ripped off"
pageid: 2503
revid: 5120
kind: repair_guide
source: "https://repair.wiki/w/Steam_Deck_-_Power_Button:_Middle_pad_ripped_off"
history: "https://repair.wiki/index.php?title=Steam_Deck_-_Power_Button:_Middle_pad_ripped_off&action=history"
permalink: "https://repair.wiki/index.php?oldid=5120"
last_edited: "2024-10-24T17:52:56Z"
contributors:
  - "DawidMurawski"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Steam Deck"
  - "Stubs"
infobox:
  Device: "Steam Deck"
  Affects_parts: "Steam Deck LCD Mainboard"
  Type: "Soldering, Part replacement, BGA"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Steam Deck - Power Button: Middle pad ripped off

## Problem description
Unfortunately the power button Switch on the Steam Deck LCD is a structurally weak component. The pads/traces under the switch can easily rip off, during a swap of the switch.
- == Solution ==

Compatible switches can be found as "Steam Deck switch", XBOX 360 pair switch", Nintendo DS switch e.g. on Aliexpress.

The switch is the same as the shoulder button switch on the controller boards.

The two outermost pins are connected to ground while the middle pin is connected to the ITE IT5570VG IC. Unfortunately the trace for the middle pin runs directly into one of the inner layers under one of the ground pads. At the moment, no testing point for the middle pin was found on the board.

A repair attempt is documented here:

https://www.ifixit.com/Answers/View/853756/Middle+pad+of+the+power+button+ripped+off.+Where+to+bridge+that+from
