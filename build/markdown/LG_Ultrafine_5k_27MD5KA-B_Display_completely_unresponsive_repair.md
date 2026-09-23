---
title: "LG Ultrafine 5k 27MD5KA-B Display completely unresponsive repair"
pageid: 1099
revid: 2546
kind: other
source: "https://repair.wiki/w/LG_Ultrafine_5k_27MD5KA-B_Display_completely_unresponsive_repair"
history: "https://repair.wiki/index.php?title=LG_Ultrafine_5k_27MD5KA-B_Display_completely_unresponsive_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=2546"
last_edited: "2024-01-14T19:04:42Z"
contributors:
  - "HaileyKitty"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for LG Ultrafine 5k 27MD5KA-B"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# LG Ultrafine 5k 27MD5KA-B Display completely unresponsive repair

## Problem description
Display is 100% unresponsive, does not charge connected device.
![Frontside of board, destroyed TPS65983](images/e/e2/Picture.png)

## Symptoms
- Display is 100% unresponsive.
- Does not charge connected device.
- Test mode works (see [LG Ultrafine 5k 27MD5KA-B](LG_Ultrafine_5k_27MD5KA-B.md) and scroll down to "How to use test mode".)
![Backside of board, charred components and layers](images/7/77/Picture2.png)

## Solution
- Test different thunderbolt 3 cables for connecting the device to the display's main thunderbolt port. The cable that came with the monitor is the best candidate.
- Test unplugging device for 10 minutes from power then plug it back in.
- Disassemble the monitor and unscrew the main board and inspect the **TPS65983BA** chip located on the same side as the USB-C ports, if there are any visible indications of damage a replacement might be necessary. The chip can be replaced with an (almost) identical **TPS65983BA** (TPS65983BAZBHR) [https://www.ti.com/lit/ds/symlink/tps65983b.pdf?HQS=dis-mous-null-mousermode-dsf-pf-null-wwe&ts=1675099119121&ref_url=https%253A%252F%252Fwww.mouser.se%252F Datasheet], I bought them on [https://eu.mouser.com/ProductDetail/Texas-Instruments/TPS65983BAZBHR?qs=byeeYqUIh0Pu5%252BF7U3SRZA%3D%3D&countryCode=DE&currencyCode=EUR Mouser]. It is the same BGA layout as CD3215 chips commonly found in more modern MacBook, seemingly called both "BGA MicroStar Junior (96)" and "NFBGA (96)". The chips should come pre-balled (mine from Mouser did) so it's a quite easy repair if you have worked with BGA before. It is not sure if the replacement chip will exhibit the same behavior after some time, this has not been documented.
