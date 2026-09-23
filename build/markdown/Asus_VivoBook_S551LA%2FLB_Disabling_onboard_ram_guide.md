---
title: "Asus VivoBook S551LA/LB Disabling onboard ram guide"
pageid: 564
revid: 1761
kind: explanatory_guide
source: "https://repair.wiki/w/Asus_VivoBook_S551LA/LB_Disabling_onboard_ram_guide"
history: "https://repair.wiki/index.php?title=Asus_VivoBook_S551LA/LB_Disabling_onboard_ram_guide&action=history"
permalink: "https://repair.wiki/index.php?oldid=1761"
last_edited: "2024-01-08T18:41:56Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for VivoBook S551LA"
  - "Explanatory guides for VivoBook S551LB"
infobox:
  Device: "VivoBook S551LA, VivoBook S551LB"
  Type: "Circuit"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Asus VivoBook S551LA/LB Disabling onboard ram guide

Disabling onboard RAM for Asus VivoBook S551LA/LB and K551LA models

This guide is valid for Asus K551LA, VivoBook S551LA and S551LB models. I used S551LB Rev: 2.2 boardview for this guide.
![S551LB 0 (Figure 1)](images/c/c6/S551LB_0.jpg)
![S551LB 1 (Figure 2)](images/5/56/S551LB_1.jpg)
![S551LB 2 (Figure 3)](images/2/21/S551LB_2.jpg)
![S551LB 3 (Figure 4)](images/0/07/S551LB3.jpg)

## Why disable the onboard ram?
We need this mod when suspect about onboard RAM chips. All onboard RAM chips must be removed. If client requires the onboard RAM, replace the RAM chips and shift back the resistors.

## Disabling onboard ram steps
- Search in Nets box for "DIMM_SEL" string.

This will list all RAM configuration lines, DIMM_SEL1-3. Initial RAM configuration is 101; RAM slot plus onboard RAM available.

See Fig.1.

- Locate DIMM_SEL1 and corresponding resistors.

Shift R2128 to R2163.

See Fig. 2.

- Locate DIMM_SEL2 and corresponding resistors.

Shift R2165 to R2169.

See Fig. 3.

- Locate DIMM_SEL3 and corresponding resistors.

Shift R2130 to R2166.

See Fig. 4.

The final RAM configuration will be 010; only RAM slot available.
