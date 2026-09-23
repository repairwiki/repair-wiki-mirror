---
title: "Acer Aspire E5-571G disable discrete GPU"
pageid: 544
revid: 1792
kind: explanatory_guide
source: "https://repair.wiki/w/Acer_Aspire_E5-571G_disable_discrete_GPU"
history: "https://repair.wiki/index.php?title=Acer_Aspire_E5-571G_disable_discrete_GPU&action=history"
permalink: "https://repair.wiki/index.php?oldid=1792"
last_edited: "2024-01-08T19:49:51Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for Aspire E5-571G"
infobox:
  Device: "Aspire E5-571G"
  Type: "Circuit"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Acer Aspire E5-571G disable discrete GPU

## Disabling the dedicated GPU
Here is how you can disable the dedicated GPU on an Acer Aspire E5-571G with Compal LA-B991P board.
![U2001 (Figure 1)](images/e/e3/U2001_acer_e5-571g.jpg)

1. Tie to ground pin 4 of U2001; can short R2017 pads. See Fig. 1.
1. This will keep GPU in reset mode; PLTRST_VGA# remains always active (0V). Nvidia graphics is no longer visible in Device Manager. The chip (U2001) could be removed too.

- This way you can diagnose Nvidia discrete graphics issue.

  - Correct repair implies GPU replacement.**

- If the client decides to use the laptop with only Intel integrated graphics, then you can remove many components from GPU area: like PU1001/1201, PQ1201-04, etc.
- Remove VRAMs and GPU if like too. You can also save all 10uF/25V capacitors (0805 size), 6 in total. All these components (apart of GPU), can be reused in other repairs.
