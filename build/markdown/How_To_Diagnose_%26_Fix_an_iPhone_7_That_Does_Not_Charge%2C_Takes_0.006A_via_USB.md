---
title: "How To Diagnose & Fix an iPhone 7 That Does Not Charge, Takes 0.006A via USB"
pageid: 1427
revid: 3116
kind: repair_guide
source: "https://repair.wiki/w/How_To_Diagnose_%26_Fix_an_iPhone_7_That_Does_Not_Charge,_Takes_0.006A_via_USB"
history: "https://repair.wiki/index.php?title=How_To_Diagnose_%26_Fix_an_iPhone_7_That_Does_Not_Charge,_Takes_0.006A_via_USB&action=history"
permalink: "https://repair.wiki/index.php?oldid=3116"
last_edited: "2024-01-20T21:20:57Z"
contributors:
  - "VCCBoardRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone 7 Plus"
  - "Repair guides for iPhone 7"
  - "Stubs"
infobox:
  Device: "iPhone 7, IPhone 7 Plus"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "BGA, Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Diagnose & Fix an iPhone 7 That Does Not Charge, Takes 0.006A via USB

## Problem description
Not Charging — Turns on but doesn't charge. Takes ≈0.006 A via USB power meter.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- Turns on but doesn't
- USB Meter show 0.006A or 0.007A
- Plugging in the cable causes the phone to turn on, but no charging symbol on the top right
- Sometimes the phone doesn't turn on at all

## Solution
### Diagnostic Steps
### **Step 1: Rule Out Parts Issues**
Test the logic board with known good parts, like a known good charging port flex and battery.

These are parts that you have previously tested and confirmed they're good. Sometimes using just new stock is not enough, because sometimes new stock is defective.

Ideally, take the board out of the housing and only plug in a screen, battery and charging port to the logic board, then plug it in to charge and check the USB meter.

This helps remove all variables, as sometimes, a bad flex can cause charging issues; rare, but it happens.

If the current is still around **0.006 A** via your USB meter, the phone turns on, but does not show charging symbol, then it's a board issue.

Generally, these scenarios are **Tristar - U4001 - Part# 610A3B.**

But to confirm, we need to do additional tests.

### Step 2: Tristar Testers (optional)
You can use a tool called "Tristar Tester", which generally works well with detecting a bad Tristar, although it's not foolproof.

These two are the most popular on the market

- Smartmod Pro Tristar Tester
- ICC Pro Tristar Tester
- JC programmer Tri-Star Tester

Both scan for charging port issue, then Tristar issue.

- If either say "Tristar Fail", it's a super high chance it's Tristar (see video at 4:21 https://youtu.be/KAMpmxeaNys?t=261)
- Although, a "Tristar Pass" can still be a bad Tristar.

Use this as one of your clues to a bad Tristar, but don't trust it to be 100% accurate.

In either case, you can continue the diagnosis process to help further confirm a Tristar issue

### Step 3: DC Power Supply Boot Up Consumption
With a DC power supply or DT880, see what is the power consumption before and after prompt to boot.

If you get current draw before prompt to boot, then it's not Tristar. See above Problem/Solution, as it will be a short on the board.

If you don't get current draw before prompt to boot, but after you prompt to boot, the first number of the current draw of the boot sequence is ≈0.150–0.250 A, then it definitely points towards a bad Tristar (see video at 6:39 https://youtu.be/KAMpmxeaNys?t=399).

### Step 4: Check Tristar for Heat (Optional)
You can also use a thermal camera or freeze spray to check if Tristar heats up when you prompt to boot. Usually it will get hot when it's bad, but not always.

### Step 5: Check Voltage at the Battery Connector
Plug in the charging port flex to the logic board, and nothing else. No screen, no battery, etc.

Then plug in the charging cable to the charging port.

Set your multimeter to DC volts mode, and measure the positive and negative battery pins of the battery connector J2201.

These are the 2 large pins on each side.

Polarity for this test doesn't matter, just ignore the negative symbol if you end up probing in reverse polarity

- If the voltage is lower than around 2 V, then Tristar is bad. Usually around 0.300–0.600 V
- A working charging circuit will show about 3.7 V

### Repair Steps
After all these tests, you can replace Tristar and see if it's solved.

Tristar for iPhone 7 and 7 Plus requires the version **610A3B**. Please make sure to use the correct version, as previous iPhone models use slightly different versions of Tristar.

  - Please Note:** Tristar on iPhone 7 and 7 Plus is partially covered by a shield. It is highly recommended that you don't touch the shield. You should be able to pull off the chip at an angle and place the new Tristar at angle. (See video at 13:22: https://youtu.be/KAMpmxeaNys?t=802)

Cutting the shield to get full access to Tristar will risk damaging surrounding components. Also, cutting the shield creates sharp points on the shield, which tend to stick out. This will cause the shield to cut or pierce through the charging port when you put it back into the housing, which will cause No Charging again.

### **After Replacing Tristar**
Once you replace Tristar, you can follow the same steps from above to confirm if it's solved.

- Check USB Charging with just your known good screen, battery, and port. It should be what a known good charging iPhone looks like. Generally 1 A or more.
- Run the Tristar Tester tool again (if you have one) and see if it passes now
- Check the first number after you prompt to boot. It should be around ≈0.045 A
- Check if Tristar still heats up with freeze spray or thermal camera
- Check if the voltage at the battery connector is at 3.7 V, per Step 5 above

You'll want to compare you previous results to the new results. This tells you if the issue was solved or there's a problem still present on the board.

  - Please note:** Each charging brick is slightly different, so it is recommended to get familiar with your charging brick and cable. Each cable and brick will give slightly different USB charging current readings based on the specs of the current output. You can read the charging brick itself to see the specs.

You can get a known good iPhone of the same model and see what the USB charging current is, then compare to the device you are repairing to see if it's about the same.

Also, batteries that are close to a full charge will charge at a lower current than a low battery. Old/worn out batteries also charge at lower rates, as they're degraded and can't take as much current.

## Other Possible Charging Faults
If it still doesn't charge after replacing Tristar, make sure you followed all the troubleshooting issues above.

Then, you'll want to check for shorts around Tristar.

You can probe both sides of each capacitor that's directly surrounding Tristar and check for continuity to ground.

It's possible that TRISTAR_BYPASS capacitor C4005 is shorted to ground. It is recommended to replace.

C4005 value: 1.0 μF, 6.3 V, 0201 package

You can also remove Tristar and diode mode all the Tristar pads.

Compare the readings on your boardview software, like ZXW to your board.

You can also compare diode mode readings to a known good board.

If you find any shorts, you'll need to inject voltage to find the shorted capacitor.
