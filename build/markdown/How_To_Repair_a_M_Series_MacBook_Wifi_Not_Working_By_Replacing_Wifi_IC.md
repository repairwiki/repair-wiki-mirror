---
title: "How To Repair a M Series MacBook Wifi Not Working By Replacing Wifi IC"
pageid: 8326
revid: 12206
kind: repair_guide
source: "https://repair.wiki/w/How_To_Repair_a_M_Series_MacBook_Wifi_Not_Working_By_Replacing_Wifi_IC"
history: "https://repair.wiki/index.php?title=How_To_Repair_a_M_Series_MacBook_Wifi_Not_Working_By_Replacing_Wifi_IC&action=history"
permalink: "https://repair.wiki/index.php?oldid=12206"
last_edited: "2025-10-01T20:08:52Z"
contributors:
  - "IamMyron07"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Air A2337"
  - "Repair guides for MacBook Pro A2338"
  - "Repair guides for MacBook Pro A2442"
  - "Repair guides for MacBook Pro A2992"
  - "Repair guides for Macbook Air A2681"
  - "Repair guides for Macbook Air A3113"
infobox:
  Device: "MacBook Air A2337, Macbook Air A2681, Macbook Air A3113, MacBook Pro A2338, MacBook Pro A2442, MacBook Pro A2992"
  Affects_parts: "Logic Board, WiFi IC"
  Needs_equipment: "Soldering Iron, Hot Air Station, LB WiFi IC, LB Programmer, LB Software"
  Type: "Soldering"
  Difficulty: "4. Specialist"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# How To Repair a M Series MacBook Wifi Not Working By Replacing Wifi IC

NOTE: Download LB Wifi OFF Software: https://fileoss.lbtool.net/webfile/lbtool-tool/LB-WIFI-OFF-1.0.0.zip

## Problem description
On MacBook models with M-series chipset (M1/M2/M3/M4), Wi-Fi can stop working due to a failed Wi-Fi IC. Even after macOS reinstall, the machine may show “Exclamation Mark on Wifi Toggle” because the Wi-Fi IC is paired to the logic board via ECID binding. Replacing the IC requires unbinding and rebinding the Wi-Fi chip to the MacBook.
## Symptoms
- Wi-Fi greyed out in macOS.
- "Exclamation mark" on WiFi
- Bluetooth may also fail in some cases.
- macOS reinstall, PRAM/SMC reset do not fix the issue.
![WiFi Not Working (Figure 1)](images/2/20/Mac-wifi-bad.png)

### Diagnostic Steps
1. Boot macOS → check if Wi-Fi toggle is unavailable.
1. Enter System Information > Wi-Fi → confirm hardware not detected.
1. Ensure issue is not antenna or connector related (inspect for corrosion/damage).
1. Verify power rails to Wi-Fi IC are present. If power is correct but IC is still not enumerating, proceed with replacement & rebinding.

### Repair Steps
#### Software Setup
1. Install [https://fileoss.lbtool.net/webfile/lbtool-tool/LB-WIFI-OFF-1.0.0.zip Luban software]  (LB-WIFI-OFF) using a pendrive.
1. Launch Luban software with internet connection (mobile hotspot works).
1. The software will unbind Wi-Fi and read the MacBook ECID automatically.![Successful WiFi Unbind](images/b/b1/Mac-wifi-unbind-successful.png)
1. Verify in “About This Mac” that serial number is correct.![Verify Serial No. is same after unbind.](images/2/2a/Mac-wifi-unbind-sn-match.png)
1. Shut down MacBook.

#### Board Work
6. Disconnect battery, remove logic board from chassis.

7. Remove Wi-Fi IC with hot air.
![Remove MacBook WiFi IC](images/2/2f/Mac-wifi-removal.png)
8. Clean solder pads using wick + flux until smooth.

#### Programming the Wi-Fi IC
9. Connect Luban programmer with Wi-Fi IC reading module.

10. Place Wi-Fi IC in the module.
![WiFi IC in LB Tool](images/b/b1/Mac-wifi-programmer-install.png)
11. Open Luban tool → wait for IC to be read.
![New LB WiFi IC reading](images/3/3e/Lbtool-wifi-reading.png)
12. Input the MacBook serial number (recorded earlier).

13. Click Check Now.
![Input Serial Number](images/f/f8/Mac-wifi-serial-input.png)
14. After verifying, Click Write Server Data.
![Write Server Data](images/b/b3/Write-server-data.png)
15. Verify if written info (Serial) is correct.

16. Confirm write.
![Verify Serial Number](images/7/71/Verify-serial.png)
17. Wait for successful confirmation.

#### Reinstallation
18. Reball Wi-Fi IC with correct stencil.

19. Install IC back onto the logic board.

20. Clean with IPA, inspect under microscope.

21. Reassemble MacBook, reconnect battery.

#### Verification
- Boot into macOS.
- Wi-Fi should now be detected and toggle enabled.
- System Information should show Wi-Fi hardware with correct addresses.
- Connect to a Wi-Fi network and run stress test (download/upload).![WiFi fixed successfully.](images/0/00/Wifi-fixed-successfully.png)
