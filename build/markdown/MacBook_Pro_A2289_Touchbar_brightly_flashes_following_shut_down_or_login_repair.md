---
title: "MacBook Pro A2289 Touchbar brightly flashes following shut down or login repair"
pageid: 83
revid: 194
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A2289_Touchbar_brightly_flashes_following_shut_down_or_login_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A2289_Touchbar_brightly_flashes_following_shut_down_or_login_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=194"
last_edited: "2023-09-26T14:47:14Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A2289"
  - "Stubs"
infobox:
  Device: "MacBook Pro A2289"
  Affects_parts: "BridgeOS/T2"
  Type: "Part replacement, Software"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A2289 Touchbar brightly flashes following shut down or login repair

## Problem description
When the touchbar flashes after shutdown or login, this will be related to corrupted BridgeOS firmware and will be resolved via a DFU revive or restore.![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Flashing touchbar

## Solution
### DFU Revive or restore BridgeOS
- Ensure you're running the latest macOS version for consistent results.
- [https://support.apple.com/guide/apple-configurator-mac/revive-or-restore-an-intel-based-mac-apdebea5be51/mac Follow the provided Apple support article for the procedure, including on how to force a Intel based MacBook into DFU mode by using a key combination.]
- **SELECTING RESTORE WILL WIPE ALL USER DATA!**
- **If a DFU Revive or Restore does not resolve the issue, try placing the board in a known good top case or replace the touchbar/top case.**

  - If the issue still is not resolved after touchbar replacement, the issue is likely related to the T2 chip's internal GPU and cannot be repaired without replacing the system board, or replacing the T2 chip. (Not recommended.)**
