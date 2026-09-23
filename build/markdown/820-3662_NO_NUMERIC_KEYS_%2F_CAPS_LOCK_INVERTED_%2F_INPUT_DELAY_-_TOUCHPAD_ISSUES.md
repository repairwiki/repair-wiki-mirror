---
title: "820-3662 NO NUMERIC KEYS / CAPS LOCK INVERTED / INPUT DELAY - TOUCHPAD ISSUES"
pageid: 6438
revid: 9792
kind: other
source: "https://repair.wiki/w/820-3662_NO_NUMERIC_KEYS_/_CAPS_LOCK_INVERTED_/_INPUT_DELAY_-_TOUCHPAD_ISSUES"
history: "https://repair.wiki/index.php?title=820-3662_NO_NUMERIC_KEYS_/_CAPS_LOCK_INVERTED_/_INPUT_DELAY_-_TOUCHPAD_ISSUES&action=history"
permalink: "https://repair.wiki/index.php?oldid=9792"
last_edited: "2025-08-03T00:43:26Z"
contributors:
  - "DiogenesElPERRO"
anonymous_edits: 0
categories:
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# 820-3662 NO NUMERIC KEYS / CAPS LOCK INVERTED / INPUT DELAY - TOUCHPAD ISSUES

![534x534px](images/c/c9/7bf703f1-22ae-4e3b-acce-5593cb357289.png)
  - 820-3662 NO NUMERIC KEYS / CAPS LOCK INVERTED / INPUT DELAY - TOUCHPAD ISSUES**

The device arrived with the numeric keys on the internal keyboard non‐functional, despite a complete keyboard replacement. Visible moisture and sulfation were detected near the keyboard’s SPI controller (U4801).

🔍 **Step-by-Step Diagnosis**

Visual inspection: Corrosion was found near the keyboard/trackpad controller area (U4801).

Voltage drop across R4814 (relevant resistor in the SPI circuit) was checked and confirmed expected values.

  - ''Chip replacement attempts:
  -   - First attempt:**

Replaced U4801 with a donor chip from board 820-3476 (MacBook A1502).

🟡 Result: Keyboard worked, but Caps Lock LED was reversed (lit when lowercase, off when uppercase).

  - Second attempt:**

Used a chip from MacBook A1278 (Unibody).

🔴 Result: Severe input delay, no trackpad and overall poor keyboard behavior.

  - Final solution:**

Replaced with U5701 from donor board 820-3332.

✅ Result: Keyboard fully functional, Caps Lock LED working properly, no delay, trackpad also fully operational.

  - ⚙️ Technical Conclusion**

The U4801/U5701 keyboard SPI controller contains firmware/configuration specific to each board model. These chips are not freely interchangeable between different MacBook series (A1278, A1502, A1398, etc.).

⚠️ **Using an incompatible IC can cause:**

Reversed Caps Lock LED logic.

Noticeable input delay on keys input.

Malfunctions with the trackpad or power button.

✅ **Key Takeaway**

“The keyboard IC (U4801/U5701) must come from a firmware-compatible logic board. Although they are electrically identical, their internal configuration depends on the board model and its interaction with the SMC.”
— Diógenes el Perro

🛠️ Note: Neither the BIOS nor the SMC were reprogrammed during this repair.
