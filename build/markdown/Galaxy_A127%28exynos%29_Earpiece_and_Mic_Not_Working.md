---
title: "Galaxy A127(exynos) Earpiece and Mic Not Working"
pageid: 4792
revid: 7890
kind: repair_guide
source: "https://repair.wiki/w/Galaxy_A127(exynos)_Earpiece_and_Mic_Not_Working"
history: "https://repair.wiki/index.php?title=Galaxy_A127(exynos)_Earpiece_and_Mic_Not_Working&action=history"
permalink: "https://repair.wiki/index.php?oldid=7890"
last_edited: "2025-06-22T12:38:48Z"
contributors:
  - "Ajimalg82"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Galaxy A12"
  - "Stubs"
infobox:
  Device: "Galaxy A12"
  Affects_parts: "Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering, BGA"
  Difficulty: "4. Specialist"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Galaxy A127(exynos) Earpiece and Mic Not Working

## Problem description
The **main microphone** and **earspeaker** are completely non-functional.

This issue typically arises **after severe physical damage**, such as **heavy drops** or **bending near the shield area**.

  - Note:** You may have already attempted replacing components like the **screen**, **dock**, or **earpiece**, but the issue persists.

![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Unable to **hear or speak** during phone calls
- **Voice memos** either cannot be recorded or are recorded **without sound**
- **Earspeaker fails** the earpiece test in the **Samsung service menu**
- **Diode readings** on the **Main FPC Connector** and **earpiece output** are within normal range

## Solution
### Diagnostic Steps
- Visible **impact damage** or **dents** on the shield near the affected area
![Damage near shield](images/a/aa/Initial_problem_a127(non_mtk).png)

- **Ground pad** under the shield is either damaged or **torn off** with the shield

- Carefully **scrape off the first (ground) layer** where shown.
  - If you observe **bubbling**, **lifted fibers**, or signs of **delamination**, proceed with the repair steps
![Delamination of 2nd layer](images/b/b8/2025_06_22_13_52_IMG_8465.PNG)

### Repair Steps
- Remove the first (ground) layer in the affected area
- Access the second layer and carefully remove the damaged and show the traces
![Traces exposed of second layer](images/0/00/2025_05_19_15_57_IMG_7935.JPG)

- Pretin the traces to make jumpers
- Mentioned the traces that go to power ic from cpu for sound functions
![traces to pmic](images/c/c5/PMIC_TO_CPU_TRACES_A127.png)

- Use 0.007mm silver jumper wire to reconstruct the connections
- Clean the area thoroughly
- Apply UV-curable solder mask to insulate the repair
