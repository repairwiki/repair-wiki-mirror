---
title: "How To Fix a MacBook Pro A1706 Stuck on 5V and boot looping"
pageid: 8404
revid: 12290
kind: other
source: "https://repair.wiki/w/How_To_Fix_a_MacBook_Pro_A1706_Stuck_on_5V_and_boot_looping"
history: "https://repair.wiki/index.php?title=How_To_Fix_a_MacBook_Pro_A1706_Stuck_on_5V_and_boot_looping&action=history"
permalink: "https://repair.wiki/index.php?oldid=12290"
last_edited: "2025-10-13T22:11:24Z"
contributors:
  - "IamMyron07"
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

# How To Fix a MacBook Pro A1706 Stuck on 5V and boot looping

## Problem description
A MacBook Pro A1706 (13-inch, Touch Bar) presents 5V and power cycling **only on USB-C** after liquid exposure near the **CD3215 USB-C controller** area.

On inspection, **resistors near the CD3215 IC** are found **corroded**, interrupting the communication and power negotiation process between the logic board and the charger.
![MacBook Pro - A1706 Corroded Resistor near CD3215](images/0/08/A1706-resistors.png)

## Symptoms
- MacBook does not power on.
- USB-C meter shows 5V only, no negotiation to 20V.
- Visible corrosion around CD3215 IC.
- USB-C meter power cycles.

### Diagnostic Steps
1. **Visual Inspection**

- Examine both **left and right CD3215 controllers** near the USB-C ports.
- Look for **corrosion, green residue, or burnt resistors** in the **LDO / CC line** areas.

  - 2. USB-C Meter Test**

- Connect charger → verify if voltage negotiates to **20 V**.

- If it stays at **5 V**, the CD3215 cannot communicate with the SMC or is missing key pull-ups.

3. **Resistance Check**

- Probe resistors connected to:

  - **CC1 / CC2 lines**
  - **LDO_1V1 / LDO_1V8**
  - **SCL / SDA communication lines**

- If any resistor reads **OL (open)** or drastically higher resistance, replace it.

4. **Communication Check**

- Inspect the LDO **resistors (typically 1 MΩ)** next to the CD3215 IC.
- If corroded, CD3215 cannot detect the charger and initiate PD handshake.

## Repair Steps
1. **Clean the Area**

- Remove conformal coating and corrosion with IPA and soft brush.
- If pads are damaged, repair traces under microscope.

2. **Replace Faulty Resistors**

- Identify corroded resistors (commonly **R3108–R3109** or nearby on CD3215 lines).
- Replace with correct values per schematic (typically 1 **MΩ** depending on the line).

3. **Inspect Capacitors**

- Check small caps near LDO and CC lines for shorts. Replace if leaky.

4. **Reflow / Replace CD3215 (if needed)**

- If corrosion extends under the CD3215 IC, reflow or replace it after cleaning pads thoroughly.

5. **Test USB-C Negotiation**

- Reconnect charger — voltage should rise to **20 V / ~0.6 A–0.8 A**, indicating successful handshake.
