---
title: "IPhone 14 Pro Max – No Modem Firmware After RF Layer Swap"
pageid: 6206
revid: 9565
kind: other
source: "https://repair.wiki/w/IPhone_14_Pro_Max_%E2%80%93_No_Modem_Firmware_After_RF_Layer_Swap"
history: "https://repair.wiki/index.php?title=IPhone_14_Pro_Max_%E2%80%93_No_Modem_Firmware_After_RF_Layer_Swap&action=history"
permalink: "https://repair.wiki/index.php?oldid=9565"
last_edited: "2025-07-31T13:00:16Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for iPhone 14 Pro Max"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone 14 Pro Max – No Modem Firmware After RF Layer Swap

## Problem description
An iPhone 14 Pro initially came in with “No Service” (no IMEI on dialer), but modem firmware was still present. The device was previously worked on by another technician who attempted to resolve the issue by swapping the RF (bottom) layer. After the swap, the phone began showing “No Modem Firmware”, making the situation worse.

This issue is due to mismatched board configuration resistors (Fig. 3) — specifically the Board ID, Platform ID, and SKU ID resistors — between the original and donor layers.

![Modem firmware blank (Figure 1)](images/1/18/No-Modem-Firmware.png)

## Symptoms
- No IMEI on dialer
- Modem firmware missing (blank under Settings > General > About) (Fig. 1)
- Cannot connect to any network

### Diagnostic Steps
1. Check for Modem Firmware:
1. * Navigate to Settings > General > About
1. * If “Modem Firmware” is blank, baseband is not initializing.
1. Confirm RF Layer Swap:
1. * Check with client or inspect board for signs of reball or swap on the RF side.
1. Inspect Board Config Resistors:
1. * Check if Board ID, SKU ID, and Platform ID resistors are missing or incorrectly placed on the donor RF layer.
1. * Use microscope + boardview/schematic to locate and match resistor values from the original board.
![2 different board revisions  (Figure 3)](images/7/72/Different-Board-Revisions.png)
![Restored modem firmware after replacing board,sku and platform ID resistors (Figure 2)](images/6/66/Modem-Firmware-Restored.png)

### Repair Steps
1. Identify Original Config Resistors:
1. * If original RF board is available, measure and note resistor values at Board ID, SKU ID, and Platform ID.
1. Transfer Resistors to Donor RF Layer:
1. * Carefully remove the config resistors from the original board.
1. * Solder them to the corresponding pads on the donor RF layer.
1. * Ensure alignment and no shorts between pads.
1. Inspect and Clean:
1. * Check for cold joints or missing components.
1. * ![Location for Board, SKU and Platform ID resistors. (Figure 4)](images/f/fc/Resistor-locations.png)Clean area with IPA and test continuity.
1. Assemble and Test:
1. * Power on the phone.
1. * Go to Settings > About and check if “Modem Firmware” appears. (Fig. 2)
1. * Dial *#06# to confirm IMEI is now visible.
1. * Test network signal and cellular connectivity.
