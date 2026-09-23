---
title: "Steam Deck - Replace shoulder switch R1/L1"
pageid: 2462
revid: 13793
kind: repair_guide
source: "https://repair.wiki/w/Steam_Deck_-_Replace_shoulder_switch_R1/L1"
history: "https://repair.wiki/index.php?title=Steam_Deck_-_Replace_shoulder_switch_R1/L1&action=history"
permalink: "https://repair.wiki/index.php?oldid=13793"
last_edited: "2026-01-29T23:21:14Z"
contributors:
  - "DawidMurawski"
  - "Razimon"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Steam Deck"
  - "Stubs"
infobox:
  Device: "Steam Deck"
  Affects_parts: "Controller Board"
  Needs_equipment: "Soldering Iron, replacement switch"
  Type: "Soldering, Part replacement"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Steam Deck - Replace shoulder switch R1/L1

## Problem description
![Figure 1: Example of a new shoulder button switch with a ripped center pad  (picture by u/veazix).](images/9/93/Shoulder_switch.webp)
A common problem with the controller board of the Steam Deck  LCD are the shoulder switches, that can break off easily during disassembly.
- == Solution ==

#### Where to buy new switches
There are multiple compatible replacement switches. On Aliexpress they are sold as

- Steam Deck switch
- XBOX 360 bluetooth pair switch

Those switches have three pins and two legs (the latter for mounting through the pcb).
### Repair Steps
![Figure 2: Test point of the L1 shoulder switch on the rev B controller board - full view. Red box: signal multiplexer. green arrow: testing point for the L1 switch.](images/5/54/REV_B_left_back_mux.jpg)
Swapping of the switches should be self-explanatory. A hot plate/pre-heater is recommended (the board sinks a lot of heat). See example videos:

https://www.youtube.com/shorts/R3DQNNDvZmE

https://www.youtube.com/watch?v=ZGT32mNI3Yk

https://www.youtube.com/watch?v=PFDZtsM-iDM

#### Damaged signal pad
In case the signal pads on the pcb get damaged (See Figure 1):

On each controller board the leftmost and rightmost pin of the switch is connected to the ground plane of the board.
![Figure 3: Test point of the L1 shoulder switch on the rev B controller board. red circle: testing point for the L1 switch.](images/a/a1/Back_board_l.jpg)
The middle pin is connected to the MCU/a signal multiplexer. On the left controller board you can strip the solder mask of the trace, running to the middle pin of the switch or connect the middle pin of the switch to the corresponding testing point for the L1 switch (see figure 2 and 3 on rev. B boards, figure 7 on rev. F board, figure 8 on rev. G board).
![Figure 4: Test point of the R1 shoulder switch on the rev. B controller board. green circle: testing point for the R1 switch.](images/3/34/R_Board_REV_B_back_-_R1_test_point.jpg)
On the right controller board, the middle pin is connected to the testing point visualised in figure 4.
![Figure 5: Controller Board R, magnet wire connected to the center pin of the switch  (picture by u/veazix).](images/4/4e/Wire1.webp)
![Figure 6: Controller Board R, magnet wire connected to the testing point on the back side of the board (picture by u/veazix).](images/8/82/Wire2.webp)
A possible fix for the right controller board might look like figure 5 and 6 (rev. B Board)  if you run a magnet wire (enamelled wire) from the center pin of the switch to the testing point.
![Figure 7: Testing point for L1 switch on controller board rev. F - left[[File:Steam Deck L Board Rev. G.jpg|thumb|Figure 8: Testing point for L1 switch on controller board rev. G - left\]\]](images/e/e3/Shoulder_switch_testing_point.jpg)
