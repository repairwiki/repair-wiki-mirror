---
title: "MacBook Pro A1706 Question mark folder or SSD not recognized repair"
pageid: 217
revid: 589
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A1706_Question_mark_folder_or_SSD_not_recognized_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1706_Question_mark_folder_or_SSD_not_recognized_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=589"
last_edited: "2023-10-30T18:44:38Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1706"
  - "Stubs"
infobox:
  Device: "MacBook Pro A1706"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station, thermal camera"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1706 Question mark folder or SSD not recognized repair

## Problem description
Question mark folder, no external boot possible & Recovery does not work on A1706 MacBook
![Figure 1](images/f/fa/Piccoloissue.jpg)

## Symptoms
- Question mark folder
- No external boot possible
- Recovery does not work

## Solution
#### Check R9350
- Examine R9350 (PICCOLO_IUVD) on the board
  - Check if R9350 is no longer soldered to the board.
  - Look for any missing pad for pin 1 (PPVIN_2V7NAND_LB). Refer to Fig 1 for visual guidance.
- Inspect the area near R9350
  - Examine the trace coming out of Terminal 1 of R9350.
  - Be cautious about the neighboring via, as it can break the trace.
- Measure the resistance of R9350
  - Ensure it is within the specified range.
- Look out for potential trace issues
  - Sometimes, the neighboring via can damage the trace, resulting in connectivity issues. Check for broken traces and continuity problems.
  - [https://www.youtube.com/watch?v=m6lTkZnykqo Example of a broken trace] (Fixed by running a wire to replace the broken trace)
  - [https://www.youtube.com/watch?v=WbuRSUitwCw Be aware of potential bad probe points, which may look good at a cursory investigation]

#### Check the Piccolo circuit
the Piccolo circuit can be sensitive to any sort of water damage in its vicinity.

- Probe inductors near the Piccolo chip. If they are shorted, replace the Piccolo chip. Injecting 1.3 V on these inductors usually won't give you a strong hotspot.
- In cases of no liquid damage, if the SSD is dead, It's probably unfixable.
- Measure C9416, Q9401, or U9400 for short circuit, it often happens due to issues with U9400 circuit
- In rare cases, there may be no damage in the R9350 area, but the TP above R9350 may lack PPVIN_2V7NAND_LB. Check the continuity between that TP and pin 43 (PPVIN_2V7NAND_LB) of J9600. In such cases, consider running a jumper wire from the closest source of PPBUS_GSH (pin 1 C6582) to the testpad after which, the SSD should now be detected.
  - After inspection and not finding any breaks in that PPVIN_2V7NAND_LB line, I deliberated on where to best access PPVIN_2V7NAND_LB from. I ran a jumper wire from pin 1 C9400 (PPVIN_2V7NAND_LB) and conformal coated that enameled jumper wire and considered it a viable repair.
- In other situations, a damaged trackpad cable can short PP3V3_S4_TPAD. This line goes through R5650 and then to R8901 as PP3V3_S4, and leaves as STORAGE_EN to go to J9600 lifeboat connector. It continues as STORAGE_LB_EN and goes to U9300 as its EN line. U9300 is the PMIC for SSD. Replacing the trackpad cable may resolve the issue.
- If the issue persists, and there was a history of liquid spill on the keyboard, disconnect the keyboard as it may be causing the problem.
