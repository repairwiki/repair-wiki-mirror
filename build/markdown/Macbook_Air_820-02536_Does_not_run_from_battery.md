---
title: "Macbook Air 820-02536 Does not run from battery"
pageid: 7708
revid: 11369
kind: other
source: "https://repair.wiki/w/Macbook_Air_820-02536_Does_not_run_from_battery"
history: "https://repair.wiki/index.php?title=Macbook_Air_820-02536_Does_not_run_from_battery&action=history"
permalink: "https://repair.wiki/index.php?oldid=11369"
last_edited: "2025-09-07T14:07:26Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Macbook Air A2681"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Macbook Air 820-02536 Does not run from battery

## Problem description
The device does only turns on and runs with the charger plugged in.

## Symptoms
- The device only turns on with the charger plugged in.
- The device turns on but does not charge the battery
### Diagnostic Steps
This problem is with the detection of the battery, this can be caused by a faulty battery or a motherboard issue.

Inspect the Battery FPC on the motherboard and on the battery for any liquid or phsycal damage, if there are any missing pins or any liquid damage replace  the FPC.
![Resistor A2681.png](images/a/a2/Resistor_A2681.png)
If there is no damage to the FPC there is a resistor "R51B1" near the webcam connector that is common to get lost if the device has been worked on before, this resistor is important and will cause issues, this resistor has a 0ohm value and 0201 size so if you dont have any on hand you can jump it and the machine will work perfectly fine.
