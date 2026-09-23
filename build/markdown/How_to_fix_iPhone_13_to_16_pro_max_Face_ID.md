---
title: "How to fix iPhone 13 to 16 pro max Face ID"
pageid: 7127
revid: 10671
kind: repair_guide
source: "https://repair.wiki/w/How_to_fix_iPhone_13_to_16_pro_max_Face_ID"
history: "https://repair.wiki/index.php?title=How_to_fix_iPhone_13_to_16_pro_max_Face_ID&action=history"
permalink: "https://repair.wiki/index.php?oldid=10671"
last_edited: "2025-08-25T21:22:49Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 13"
  - "Repair guides for iPhone 13 Mini"
  - "Repair guides for iPhone 13 Pro"
  - "Repair guides for iPhone 13 Pro Max"
  - "Repair guides for iPhone 14"
  - "Repair guides for iPhone 14 Plus"
  - "Repair guides for iPhone 14 Pro"
  - "Repair guides for iPhone 14 Pro Max"
  - "Repair guides for iPhone 15"
  - "Repair guides for iPhone 15 Plus"
  - "Repair guides for iPhone 15 Pro"
  - "Repair guides for iPhone 15 Pro Max"
  - "Repair guides for iPhone 16"
  - "Repair guides for iPhone 16 Plus"
  - "Repair guides for iPhone 16 Pro"
  - "Repair guides for iPhone 16 Pro Max"
infobox:
  Device: "iPhone 13, iPhone 13 Mini, iPhone 13 Pro, iPhone 13 Pro Max, iPhone 14, iPhone 14 Plus, iPhone 14 Pro, iPhone 14 Pro Max, iPhone 15, iPhone 15 Plus, iPhone 15 Pro, iPhone 15 Pro Max, iPhone 16, iPhone 16 Plus, iPhone 16 Pro, iPhone 16 Pro Max"
  Affects_parts: "TrueDepth Camera"
  Needs_equipment: "JC Programmer, JC Non Removal Face ID tag-on flex, PC"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How to fix iPhone 13 to 16 pro max Face ID

## Problem description
Face ID stops working because the TrueDepth sensor module is shorted.

This is most often caused by:

- Water damage
- Accidental damage while the device is open during other repairs (e.g., display replacement, battery replacement etc.)

## Symptoms
- Settings → About → Parts & Service History → “Issue with Face ID detected”
- Unable to set up Face ID
- Face ID unavailable
![Unable to setup Face ID](images/b/bd/Unable-to-setup-faceid.png)
## Diagnostic Steps
1. Attempt to set up Face ID in Settings → Face ID & Passcode.
1. Confirm history of water damage or previous repair work with the customer.
1. Inspect the TrueDepth module for visible damage or corrosion.

## Repair Steps
1. Open the iPhone and disconnect/remove the TrueDepth camera module.
1. Power on the phone without the module connected and connect it to a PC.
1. Open JC Repair Assistant on the PC and connect a JC V1S Pro or V1SE programmer. [You will need [https://www.diyfixtool.com/products/jcid-iphone-13-16-face-id-repair-tag-on-fpc-activation-board?srsltid=AfmBOoqwf36a-mVB3p8K7Fh2yab9pB1hK2pTHb8EGty47QR_I6QD_2bo&variant=47556754473189 13-16 Series Face ID Activation / Read & Write Adaptor]]
1. Perform a cloud backup of the TrueDepth module data using JC software.
1. Test TrueDepth module and confirm module fuses.![Face ID showing Fused](images/0/0f/Abnormal-faced.png)
1. Click Activate and wait until the process completes.
1. Connect the respective Tag-on flex cable to the JC programmer.
1. Write the corresponding device Face ID data onto the flex from the backup.
1. Verify that the flex shows the original TrueDepth data.
1. Connect the Tag-on flex to the TrueDepth module and recheck in JC software/programmer: Should now show “NORMAL” instead of “FUSED”.![Face ID Normal](images/b/b0/Normal-faceid.png)
1. Fold the Tag-on flex according to your iPhone model (follow JC’s reference videos).
1. Reinstall the TrueDepth module with the Tag-on flex attached.
1. Power on the phone and verify that Face ID is fully functional.![Face ID successfully setup](images/9/9a/Face-id-success.png)
