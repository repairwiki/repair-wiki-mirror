---
title: "Raspberry Pi LAN9514"
pageid: 974
revid: 2328
kind: explanatory_guide
source: "https://repair.wiki/w/Raspberry_Pi_LAN9514"
history: "https://repair.wiki/index.php?title=Raspberry_Pi_LAN9514&action=history"
permalink: "https://repair.wiki/index.php?oldid=2328"
last_edited: "2024-01-13T20:51:41Z"
contributors:
  - "ASRepairs"
  - "HaileyKitty"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for Raspberry Pi"
infobox:
  Device: "Raspberry Pi"
  Type: "Circuit"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Raspberry Pi LAN9514

The LAN9514 is a chip that is found in the following [Raspberry Pi](Raspberry_Pi.md) models:

- Raspberry Pi **1** (B+)
- Raspberry Pi **2** (all)
- Raspberry Pi **3** (model B only)

The chip provides a four-port USB hub as well as ethernet functionality. It interfaces with the Pi's CPU via an internal USB connection.

## Before soldering in a new chip
- Measure the resistance between ground and the `USBDM0` pad as well as the `USBDP0` pad. The resistance should be about 1 MΩ in both cases. If the resistance is way smaller (e.g. 80 Ω), the Pi's CPU is broken, and soldering in a new chip won't solve the issue.

## References
1. [↑](LAN9514_%28Raspberry_Pi%29.md) *[https://ww1.microchip.com/downloads/en/devicedoc/00002306a.pdf LAN9514 datasheet]*, Microchip Technology Incorporated, 2016
