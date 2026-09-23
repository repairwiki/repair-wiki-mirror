---
title: "Raspberry Pi MXL7704"
pageid: 973
revid: 2327
kind: explanatory_guide
source: "https://repair.wiki/w/Raspberry_Pi_MXL7704"
history: "https://repair.wiki/index.php?title=Raspberry_Pi_MXL7704&action=history"
permalink: "https://repair.wiki/index.php?oldid=2327"
last_edited: "2024-01-13T20:51:23Z"
contributors:
  - "ASRepairs"
  - "HaileyKitty"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for Raspberry Pi"
infobox:
  Device: "Raspberry Pi"
  Type: "Circuit"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Raspberry Pi MXL7704

The MXL7704 is a programmable quadruple step-down DC/DC converter that is used in the following [Raspberry Pi](Raspberry_Pi.md) models:

- Raspberry Pi **3** (A+ and B+) (*MXL7704-R3* version)
- Raspberry Pi **4** (all) (*MXL7704-P4* version)

The MxL7704-AQB, MxL7704-XQB, MxL7704-R3 and MxL7704-P4 might be replaceable by the one-time programmable (OTP) successor MxL7704-BQB

The new model may be (one time) programmable to match the specific raspberry pi model default values.

## Common cause of failure
If the Pi's 5V pin is shorted to the neighboring 3.3V pin, the MXL7704 will try to clamp the voltage on the 3.3V line. This destroys the MXL7704 chip, leaving the 3.3V line permanently shorted to GND.

## Configuring
The MXL7704 chip can be configured via an I²C interface. The I²C address depends on the version of the chip:

| Version | Address |
| --- | --- |
| AQB and XQB versions | `0x2D` |
| R3 version (Raspberry Pi 3) | `0x1D` |
| P4 version (Raspberry Pi 4) | `0x1B` |

Despite having a different I²C address, the R3 version of the chip will be correctly recognized by the OS if it's installed in a Raspberry Pi 4.

Note that **any changes made to the configuration are not permanently stored.** Every time the chip is powered off, its default configuration is restored. Different versions of the chip have different default configurations:

| Model | Default configuration |
| --- | --- |
| Raspberry Pi 3 (A+ and B+) |  pi@raspberrypi:~ $ i2cdump -y 1 0x1d 0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f    0123456789abcdef 00: a0 01 e4 27 43 57 27 00 00 00 02 00 XX XX XX XX    ???'CW'...?.XXXX 10: a5 a5 5a c0 c0 e4 1f 48 10 a9 7f 67 00 00 XX XX    ??Z????H???g..XX |
| Raspberry Pi 4 |  pi@raspberrypi:~ $ i2cdump -y 1 0x1b 0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f    0123456789abcdef 00: a0 01 e4 27 43 57 27 00 00 00 02 00 XX XX XX XX    ???'CW'...?.XXXX 10: a5 a5 5a b0 a5 e4 de 48 10 e9 5e 66 00 27 XX XX    ??Z????H??^f.'XX |

Here's the meaning of the two default configurations (for more info, see the datasheet linked at the bottom of the page):

| Address | Setting | Raspberry Pi 3A+ / 3B+ | Raspberry Pi 4 |  |  |
| --- | --- | --- | --- | --- | --- |
|  |  | **Value** | **Meaning** | **Value** | **Meaning** |
| `0x02` | Phase interleaving | `0xe4` | 1 → 2 → 3 → 4 | `0xe4` | 1 → 2 → 3 → 4 |
| `0x10` | V_out LDO | `0xa5` | 3.3V | `0xa5` | 3.3V |
| `0x11` | V_out buck 1 | `0xa5` | 3.3V | `0xa5` | 3.3V |
| `0x12` | V_out buck 2 | `0x5a` | 1.8V | `0x5a` | 1.8V |
| `0x13` | V_out buck 3 | `0xc0` | 1.2V | `0xb0` | 1.1V |
| `0x14` | V_out buck 4 | `0xc0` | 1.2V | `0xa5` | 1.03V |
| `0x15` | Buck Sequence Group Assignment | `0xe4` |  * 1: group 0 * 2: group 1 * 3: group 2 * 4: group 3 | `0xe4` |  * 1: group 0 * 2: group 1 * 3: group 2 * 4: group 3 |
| `0x16` |  * LDO Sequence Group Assignment * Channel Enables | `0x1f` |  * group 0 * all enabled | `0xde` |  * group 3 * bucks enabled, LDO disabled |
| `0x17` |  * SEQ EN Assign * PG1 Routing | `0x48` |  * SEQ EN: group 1 * PG1 Routing: buck 4 | `0x48` |  * SEQ EN: group 1 * PG1 Routing: buck 4 |
| `0x18` | PG2 Routing | `0x10` | buck 4 | `0x10` | buck 4 |
| `0x19` |  * Fault Actions * Down Sequencing * Frequency | `0xa9` |  * Reset whole chip if any channel faults * Soft power off disabled * 78 Ω discharge enabled * 1.81 MHz | `0xe9` |  * Reset whole chip if any channel faults * Soft power off enabled * 78 Ω discharge enabled * 1.81 MHz |

The following pads can be used to access the I²C interface:

| Model | SDA | SCL |
| --- | --- | --- |
| Raspberry Pi 3 (A+ and B+) | `PP60` | `PP59` |
| Raspberry Pi 4 | The relevant traces![MXL7704 location on Raspberry Pi 4](images/2/24/768px-MXL7704_I2C_interface.jpg) |  |

## Compute Module 4 (CM4)
Since the LDO VIN is shorted to ground by CM4's layout design, the MxL7704-P4 (where the LDO is disabled by default programming) has to be used.

When using the MxL7704-R3 variant (which is the one available in AliExpress), the CM4 **will not start** since the LDO is assigned to group0 and cannot start - so group0 cannot start. With it all the buck converters stay disabled.

A tested alternative for using MxL7704-R3 for repairing CM4 is to disconnect Pin8 (LDO) and Pin7 (VIN) from the board and connect it (Pin7) permanently with +5V instead.

## References
1. [↑](MXL7704_%28Raspberry_Pi%29.md) *[https://assets.maxlinear.com/web/documents/mxl7704.pdf MXL7704 datasheet]*, MaxLinear, Inc., 2018
1. [↑](MXL7704_%28Raspberry_Pi%29.md) *[https://assets.maxlinear.com/web/files/changenotifications/pdn-20012a%20multiple%20mxl%20exar%20parts%20product%20discontinuation%20notification-1033.pdf MXL7704 Product Discontinuation Notice]*, MaxLinear, Inc., 2021
1. [↑](MXL7704_%28Raspberry_Pi%29.md) *[https://assets.maxlinear.com/web/documents/mxl7704-b.pdf MXL7704-BQB datasheet]*, MaxLinear, Inc., 2022
