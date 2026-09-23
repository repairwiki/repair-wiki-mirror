---
title: "How To Fix an iPhone SE 2020 with No Touch and/or 3 Min Restart, Mic1 Problem"
pageid: 269
revid: 720
kind: repair_guide
source: "https://repair.wiki/w/How_To_Fix_an_iPhone_SE_2020_with_No_Touch_and/or_3_Min_Restart,_Mic1_Problem"
history: "https://repair.wiki/index.php?title=How_To_Fix_an_iPhone_SE_2020_with_No_Touch_and/or_3_Min_Restart,_Mic1_Problem&action=history"
permalink: "https://repair.wiki/index.php?oldid=720"
last_edited: "2023-11-05T22:14:06Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone SE 2020"
infobox:
  Device: "IPhone SE 2020"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Soldering Iron, Hot Air Station, Insulated Jumper Wire"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Fix an iPhone SE 2020 with No Touch and/or 3 Min Restart, Mic1 Problem

## Problem description
The iPhone SE 2020 (aka iPhone SE 2nd Gen) is known to have a common issue where you have No Touch and/or 3 Min restart. This can develop on its own, out of nowhere. It can happen after a hard drop.

Both problems are due to the same board design defect. There are 3 lines that run under the SIM tray, that tend to break within the PCB layers. These 3 lines are responsible for Mic1 (a sensor required to be detected by the CPU) and touch.

- SPI_AP_TO_TOUCH_CS_CONN_L
- I2C1_AP_SCL
- I2C1_AP_SDA

## Symptoms
You will either see one or both of these symptoms. Sometimes you will see one happen first then after some time, the 2nd one starts happening.

    - No Touch** - You will experience either completely No Touch whatsoever. Or sometimes you will get intermittent touch, where it will work fine then out of nowhere, no touch at all, then back to working. Even with a new screen, it will have the same issues of the Touch Screen not working

    - 3 Min Restart** - You will experience that the phone is restarting on its own, every 3 minutes. It will sometimes feel like it's randomly restarting on its own.

## Solution
### Diagnostic Steps
First, you have to determine what is causing the issue.

  - No Touch**

- Make sure to test with known good screen
- Diode Mode the LCD connector line: SPI_AP_TO_TOUCH_CS_CONN_L
  - If it's OL, then you have a board issue
  - If you get a reading of 0.366 in Diode Mode, try putting pressure on the SIM Tray area to see if the value fluctuates.
    - If it does, then you have a board issue

  - 3 Min Restart**

- Check the panic log to see what is causing the restarting issue. You can read more about that here: [How To Fix an iPhone SE 2020 That Randomly Restarts](How_To_Fix_an_iPhone_SE_2020_That_Randomly_Restarts.md)
- If you get "Missing Sensors: mic1", then you need to first test with a known good charging port flex.
  - Make sure you're using high quality parts. Ideally an OEM Pull. Or Premium.
  - Test with known good parts as well.
- Diode Mode the Charging Port connector lines
  - I2C1_AP_SCL
  - I2C1_AP_SDA
- If either of the 2 lines above read OL, then you have a board issue
- If both of the 2 lines above give a good reading of 0.329 in diode mode, then try putting pressure on the SIM tray area of the board to see if the values fluctuate.
  - If it does, then you have a board issue.

### Repair Steps
To fix the 2 issues above, where it has been narrowed down to a board issue, you'll need to run 3 long jumpers to effectively bypass the issue & reinforce the connections so the issue is permanently solved.

It is recommended you run all 3 jumpers for every case. Regardless if you're exhibiting all the symptoms. In other words, if you have No Touch, run all 3 jumpers. If you have 3 min restart, run all 3 jumpers.

This can be tricky, but follow these instructions in this order for the easiest & most practical way to fix it

    - Jumper 1: SPI_AP_TO_TOUCH_CS_CONN_L**

You'll need to run the jumper from the LCD connector at C5770 and run it to a trace within the layers of the PCB. You can find a good spot between the SIM tray and U3600. You'll need to dig 1 layer deep to find it. Use your boardview software to see where the trace is located.
![iPhone SE 2020 - Location of iPhone SE 2020 No Touch and where it needs to be dug out from](images/a/ad/IPhone_SE_2020_No_Touch.png)
![iPhone SE 2020 - No Touch Long Jumper path](images/f/f9/IPhone_SE_2020_-_No_Touch_Long_Jumper_path.png)
Once the jumper is installed & diode mode reading is back to normal, UV mask the jumper wire so it doesn't get accidentally damaged in the future by another technician
    - Jumper 2: I2C1_AP_SCL**

Run a jumper from R6610 (next to the CPU) to C6456 (next to the charging port FPC)
![iPhone SE 2020 - Where to run the jumper from R6620 for I2C1_AP_SCL](images/2/25/IPhone_SE_2020_-_R6610_I2C1_AP_SCL_Jumper_Path.png)
![iPhone SE 2020 C6456 Jumper Location](images/a/a6/IPhone_SE_2020_C6456_Jumper_Location.png)
    - Jumper 3: I2C1_AP_SDA**

Run a jumper from R6611 (next to the CPU) to C6466 (next to the charging port FPC)
![iPhone SE 2020 R6611 Jumper Location & path](images/5/59/IPhone_SE_2020_R6611_Jumper_Location.png)
![iPhone SE 2020 C6466 Jumper Location & path](images/b/ba/IPhone_SE_2020_C6466_Jumper_Location_&_path.png)

Once you have installed all 3 jumpers, verify the Diode Mode readings are no longer OL. Also make sure they're not shorted (0.000).

Then move onto testing with known good parts.

If you have touch working, go to the stopwatch and run it. If it goes past the 3 minute mark, then it's solved.
