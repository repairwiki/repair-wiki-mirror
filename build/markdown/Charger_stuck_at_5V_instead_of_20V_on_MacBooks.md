---
title: "Charger stuck at 5V instead of 20V on MacBooks"
pageid: 177
revid: 610
kind: explanatory_guide
source: "https://repair.wiki/w/Charger_stuck_at_5V_instead_of_20V_on_MacBooks"
history: "https://repair.wiki/index.php?title=Charger_stuck_at_5V_instead_of_20V_on_MacBooks&action=history"
permalink: "https://repair.wiki/index.php?oldid=610"
last_edited: "2023-10-30T19:13:18Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Apple Laptops"
  - "Explanatory guide"
infobox:
  Type: "Circuit"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Charger stuck at 5V instead of 20V on MacBooks

USB-C MacBooks get charged through their USB-C ports, using USB-C PD standard which allows to deliver high power through a USB-C connector by raising the voltage higher than the regular 5 volts we've been used to on legacy USB ports. This requires a handshake between the laptop and the charger through a dedicated data bus, so that the charger can tell the laptop what its capabilities are, and so the laptop can then request a higher voltage, if available.
- PP3V3_G3H missing due to a short circuit on the input to PP3V3_G3H creation circuit
- Corroded LDO capacitor for PP3V3_G3H around a CD3215. On boards with 4 ports, on right side of board, check under shielding by SSD under the right CD3215 for hidden corroded capacitor.
- PP3V3_G3H missing due to PM_EN_P3V3_G3H missing due to bad ISL9239
- PP3V3_G3H missing due to CHGR_EN_MVR missing due to bad ISL9240. ISL9240 is not available for purchase. Donor would be required. Watch this troubleshooting video on similar 15" model (A1990) https://www.youtube.com/watch?v=HJ2jyo7pAmE
- PPVIN_G3H_P3V3G3H missing due to a short to ground, check D6902 if PP3V3_G3H voltage drops lower than 3.4V after fixing PPVIN_G3H_P3V3G3H short
- Bad CD3215
- Bad CD3215 ROM chip (U2890)
- Corroded probe points on the data lines between ROM chip and CD3215
- Corroded resistors around ROM chip (U2890 or UB090) affecting communication between ROM chip and CD3215
- Corrupted T2 firmware (when applicable)
If the issue is a bad CD3215, one way to get an idea, is to see which does not boot loop. When you plug the charger in with the USB-C current meter, it will turn on for 2-3 seconds, then turn off and turn on again. Whichever port doesn't boot loop usually has an associated CD3215 that is bad. Also, the bad CD3215 will occasionally get hotter than the rest.

CD3215s are chips made by Texas Instruments specifically for Apple, and are likely custom versions of their TPS65986 chip. Texas Instruments do not sell them, so replacement chips must be taken off donor boards.

There are multiple revisions of them, CD3215B, CD3215C, ... They are not compatible with each other, so make sure that you always replace a CD3215 with one from the same revision.

Troubleshooting CD3215s:
- Check presence of PP3V3_G3H, required to power the chip
- Check presence of all 4 LDOs (3.3V, 1.8V, 2, 1.1V)
- If an LDO is missing, check for short
- If no short, and only the 1.1V LDO is missing, it can be because the CD3215 can't load its firmware. Typically this also makes that USB port to not bootloop. Two options:
  - It is the master CD3215, directly connected to the SPI ROM. In that case, check continuity of SPI bus signals, possibly look at them with a scope while applying power to the board
  - It is the slave CD3215, not directly connected to the SPI ROM. In that case, it will request firmware to the other CD3215 through UART port (UPC_XX_UART_TX and UPC_XX_UART_RX). In that case, it is possible that the other CD3215 is bad
- If other LDOs are missing but no short, replace the CD3215
- Once all CD3215s have all LDOs up, then it's a matter of talking to the SMC. Check I2C bus signals for activity.
- Can also be a dead / bad ISL9239

T2 firmware can also cause the machine to be stuck at 5V. It is however, important to rule out other possible causes for the issue before re-flashing T2 firmware. Typically machines that have corrupted T2 firmware will be stuck at 5V 0.0A and typically will have PPBUS present and PP3v3_S5 missing. PP5V_S5 will often be present. T2 firmware can be re-flashed via Apple Configurator 2, however this will erase data in most cases. Try a "soft" re-flash first by clicking Advanced Options > Revive Device in Apple Configurator 2.
