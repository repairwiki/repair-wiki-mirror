---
title: "MacBook Pro A1706 Critical Software Update failed to install"
pageid: 2254
revid: 4652
kind: other
source: "https://repair.wiki/w/MacBook_Pro_A1706_Critical_Software_Update_failed_to_install"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A1706_Critical_Software_Update_failed_to_install&action=history"
permalink: "https://repair.wiki/index.php?oldid=4652"
last_edited: "2024-08-19T20:45:15Z"
contributors:
  - "ASRepairs"
  - "ProMoe"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1706"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A1706 Critical Software Update failed to install

## Problem description
[[File:Critical update error message .jpg|thumb|[https://developer.apple.com/forums/content/attachment/374c7338-f44e-4c6d-a205-93f6e2bfa0d1 Example] image (Figure 1) -- No image yet. Help expand this page by uploading it!]]

## Symptoms
- Symptom 1 (Figure 1)
- Symptom 2

## Solution
### Diagnostic Steps
- Bad Touchbar. Unplug Touchbar and try to update again.
- Bad camera caused by Flexgate, unplug LCD and try to update again on external display.
- Bad touchID, the T1 chip controls the touchID so in theory a bad touchID could cause this error although unconfirmed.
- Format drive and install MacOS. If data is required, boot into safe mode by holding shift and transfer data off.
- If you have tried all of that, then it is most likely a board related issue caused by either bad PMIC or bad T1 chip. Measure all U4200 buck outputs.
- PP1V8_Sleep3_Buck3 pulled down by corrosion under U4200/T1 PMIC. Fixed by reballing PMIC. This was also causing the Macbook to take a long time to post.
- Additional Troubleshooting steps - https://logi.wiki/index.php/Critical_Update_Required_Troubleshooting
- Could be as well a problem with the T1 chip. It will also cause the machine to take a long time to post.
- Check each pin on Touch Connector  J4402 and compare the numbers to OBD.
- Check each pin on Display connector J4401 and compare the numbers to OBD.

### Repair Steps
