---
title: "Apple ACE2 Controllers"
pageid: 8257
revid: 12249
kind: device
source: "https://repair.wiki/w/Apple_ACE2_Controllers"
history: "https://repair.wiki/index.php?title=Apple_ACE2_Controllers&action=history"
permalink: "https://repair.wiki/index.php?oldid=12249"
last_edited: "2025-10-06T11:36:45Z"
contributors:
  - "David.Lecomte"
anonymous_edits: 0
categories:
  - "Apple"
  - "Apple Laptops"
  - "Device"
  - "Laptops"
infobox:
  Manufacturer: "Apple"
  Has_code_name: "ACE2"
  Device_type: "Laptop"
  Device_release_date: "2019"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Apple ACE2 Controllers

The Apple ACE2 controllers are the second generation of USB-C PD controllers. They first appeared in 2019 with the release of the A2141 (Macbook Pro 16") and the A2159 (Macbook Pro 13" 2 Thuderbolt ports). They replace the previous generation ACE1 controllers (CD3215), and have various declinations: CD3217B12, CD3217B13 and CD3218B12, which all have the same working principles.

These controllers are also found on iPads, but due to the lack of experience of the author with these devices, this page is dedicated to ACE2 controllers on Macbooks. Whether some of that information can carry to iPads is very likely, but untested.

These chips are made specifically by [https://www.ti.com Texas Instruments] for Apple, and have no public documentation. However, the ACE1 controllers were an almost copy of the TPS65982 PD controllers, sold by TI to the public, and that have a [https://www.ti.com/lit/ds/symlink/tps65982.pdf?ts=1758735586177&ref_url=https%253A%252F%252Fwww.mouser.co.uk%252F spec-sheet]. Experience in studying the ACE2 shows that a lot of things explained in that document do carry over to these chips, and it can be used to reliably explain some of their behaviours.

On Apple laptops, every USB-C receptacle is connected to an ACE2 controller, and the Magsafe 3 connector, when present, as well. In this document, we will use the terminology "n-port device" to refer to a device that has n ACE2 controllers. For example:

- Example 1: The A2159 has 2 USB-C receptacles and no Magsafe 3. It is a 2-port device.
- Example 2: The A2442 has 3 USB-C receptacles and one Magsafe 3. It is a 4-port device.
- Example 3: The A2681 has 2 USB-C receptacles and one Magsafe 3. It is a 3-port device.

## I. Function
The ACE2 controller carries 3 main functions:

- Inrush limiter, integrated inside the IC (as opposed to the ACE1, which controlled external MOSFETS).
- PD controller, responsible for negotiating input voltage with the charger, according to the USB-C Power Delivery (PD) standard. The normal negotiated voltage on Macbooks is 20V.
- USB-C multiplexer: Detecting the type of device connected, and redirecting the trafic to the appropriate subsystem of the logic board.

Apple made the choice of not having any kind of USB-C functionality if one ACE2 controller is missing: they are meant to work together.

## II. Vanilla and OTP-ed controllers
The ACE2 controller is capable of acting as an I2C host to two masters, and can configure two I2C interfaces:

- Port 1, carried by pins `B5`, `A4` and `D7`, respectively for `SDA`, `SCL` and `IRQ`. This interface is controlled by the Thunderbolt controller, which is part of the Intel PCH or Apple Silicon SOC, depending on the architecture.
- Port 2, carried by pins `B7`, `A6` and `C8`, respectively for `SDA`, `SCL` and `IRQ`. This interface is controlled by the SMC, which is part of the T2 SOC or Apple Silicon SOC, depending on the architecture.

The I2C interfaces are set up by the IC's boot code, after it is powered on either from `VBUS` or `VIN_3V3`. The way these interfaces are set up depends on the type of controller, of which there are two:

- **Vanilla**: These are capable of acquiring up to 8 different addresses on Port 1, and 32 different addresses on Port 2, according to configuration resistors (straps) that are placed on the board, after they are powered up.
- **OTP-ed**: These have their I2C addresses burned in, and once placed on any board, will ignore the straps that are near their landing pad.

"OTP" stands for "One Time Programmed" and appears in multiple instances in board schematics. The "vanilla" terminology is not official, and was just arbitrarily decided by David Lecomte, during the time he spent researching how to replace defective ACE2s, because they are unmodified by Apple.

### II.1 Determination of type
Vanilla and OTP-ed controllers are indistinguishable physically: they all carry the same markings on the surface of the chip. When using an ACE2 to replace a defective one, it is important to know of what type it is, as using the wrong type on the wrong landing pad might create an I2C addressing conflict, that will take down the whole USB-C communication system.

#### II.1.1 ACE2 pulled from a donor board
If the origin of the ACE2 controller is known, the following rules apply:

- 2-port devices have vanilla controllers.
- On 3 or 4-port devices, the ACE2 controllers for the two USB-C receptacles on the left are vanilla, the other ACE2s are OTP-ed.

#### II.1.2 ACE2 purchased as new
Anecdotal evidence (from experience, with no counterexample so far) seems to indicate that these ICs are vanilla, if the seller is telling the truth.

#### II.1.3 ACE2 of unknown origin
When purchasing pulled ACE2s, or when harvesting them from donor boards and putting them all in a box, the origin of the chip becomes unknown. If intending to use one to replace a defective ACE2, there are methods that would allow you to determine whether it is OTP-ed or vanilla. But it is more time efficient to directly use it, following the procedure in this document: if the board is fixed, you had a vanilla; if the board is not fixed, you had either an OTP-ed, or something was damaged in the process, or your board diagnosis was incorrect (the board has another issue than the ACE2 you replaced).

The foolproof method requires some equipment: a 2-port functional Macbook board stripped of both ACE2s (pads cleaned of course), and an I2C scanner such as the JC Rbox. Referring to the schematic and boardview for that board, locate the ACE2 landing pad that has `ADDR` strapped to `GND`. Install your unknown ACE2 onto that pad. Power it from `VIN_3V3`. Then scan the I2C Port 1 with your scanner. If it reports that 0x38 is present, then your ACE2 is vanilla. Any other value (and in particular 0x3A, 0x3B and 0x3C which are the main OTP addresses used by Apple) indicates that your ACE2 is OTP-ed to that address.

### II.2 I2C addresses decoding
The vanilla ACE2 controller uses 3 pins to encode the I2C addresses for Port 1 and Port 2. We refer to pin numbers, rather than net names or pin names, because these tend to depend on the author of each schematic. The names can change, but the pin numbers don't. These pins are:

- `M19`, which we will call `ADDR`. This pin is connected to `GND` through a resistor, or floating, and is assigned a binary value depending on the value of that resistor, according to the table:

| Resistor value | `ADDR` |
| --- | --- |
| 0Ω | 000 |
| 38.3kΩ | 001 |
| 84.5kΩ | 010 |
| 140kΩ | 011 |
| 205kΩ | 100 |
| 280kΩ | 101 |
| 374k | 110 |
| Infinite (floating) | 111 |

- `B15`, which we will call `CNTL1`. This pin is assigned the value 0, or 1, depending on whether it is pulled to `GND` or to `LDO_3V3` respectively.
- `A16`, which we will call `CNTL2`. This pin is assigned the value 0, or 1, depending on whether it is pulled to `GND` or to `LDO_3V3` respectively.

The binary I2C addresses for ports 1 and 2 are then determined according to the following:

Port 1 address: 111`ADDR`

Port 2 address: 1`CNTL2` `CNTL1` `ADDR`

It is usually more convenient to then translate these addresses in hexadecimal, as this is how they are referred to in schematics.

### II.3 Example of I2C address decoding
Refer to the schematic of the A2442, page 31. The ACE2 controller `U5500` has

- `ADDR` (`UPC5_I2C_ADDR`) floating, since this pin goes to `R5650` which is not present on the board. This sets `ADDR` = 111.
- `CNTL1` (`I2C_UPC5_SCL`) pulled to `LDO_3V3` (`PP3V3_UPC5_LDO`)through a 1MΩ resistor. This sets `CNTL1`=1.
- `CNTL2` (`I2C_UPC5_SDA`) pulled to `GND` through a 1MΩ resistor. This sets `CNTL2`=0.

Thus, if one were to install a vanilla ACE2 in that position, its I2C addresses would be:

Port 1 address: 111111b = 0x3F.

Port 2 address: 101111b = 0x2F.

## III. Replacing ACE2 controllers
### III.1 Introduction, and motivation.
The method for replacing ACE2 controllers has eluded technicians for 6 years and there were widely diverging reports, even from renowned technicians about how these ICs should be replaced. There was a consensus that these ICs are programmed, and they were behaving like the programming was tied to the device, or the ROM, or the status (Master / Slave), or something else that could not be explained logically. In September 2025, [https://www.youtube.com/@LecomteRepairServices David Lecomte] announced that he had made a major breakthrough, by being able to replace UG400 on an A2442, using an ACE2 coming from an A2338, and get a fully working device. Up until that time, this was thought to be impossible. He then explained in a series of videos the theory behind the success, and proceeded to showing how all four ACE2s can be replaced on these devices, using vanilla ICs.

The following method is just a recipe to be followed, and it is highly recommended that you watch the whole playlist [https://www.youtube.com/@LecomteRepairServices/playlists ACE Controller BS], to understand how and why it works, and how to fix lingering issues that might occur after replacing the IC.

The method has not been tested on all devices, since David was alone to experiment. If you want to know only what has to be done, known-tested procedures will be posted further in this paragraph.

Now, here is an explanation in English of what is happening when trying to replace ACE2 controllers, and why we have such a complicated procedure. Apple surrounds the landing pads of OTP-ed ACE2s with configuration resistors for `ADDR`, `CNTL1` and `CNTL2` that do not correspond to the address required by the I2C map. More precisely, the I2C addresses corresponding to this configuration are conflicting with the address of another ACE2 controller on the board. This strapping is of course ignored by the OTP-ed controller installed by Apple. However, when replacing that controller with another one, either one of three things may happen:

- The new ACE2 is OTP-ed with the same addresses as the one it is replacing. Then the USB-C PD system will work right away.
- The new ACE2 is OTP-ed with another address than the one it is replacing. This address will either conflict with an already present ACE2, or it won't correspond to the I2C map. Either way, the whole USB-C system is down.
- The new ACE2 is vanilla. It will acquire the address imposed by the configuration resistors, which conflicts with another ACE2's address, and the whole USB-C system is down.

To give a concrete example (refer to the schematic): take U5500 on an A2442, for which we already computed (paragraph II.3) the addresses imposed by the surrounding resistors: they are 0x3F and 0x2F. But the I2C maps on pages 56 and 57 of the schematic tell us that it is OTP-ed with addresses 0x3A and 0x3A. Assume we replace U5500 with another ACE2 controller. Then one of three things can happen:

- The new ACE2 is OTP-ed with addresses 0x3A and 0x3A. Then the board will work right away.
- The new ACE2 is OTP-ed as 0x3B and 0x3B, or 0x3C and 0x3C. Then it will conflict with UG400 which already has addresses 0x3B; or it doesn't correspond to the I2C map, which doesn't include 0x3C. Either way, the whole USB-C system is kaput.
- The new ACE2 is vanilla. It will acquire addresses 0x3F and 0x2F, conflicting with UF500 on the AP_I2C0 bus. USB-C system is down.

This is why most attempts at replacing U5500 have failed: it would only work with an ACE2 that is OTP-ed exactly the same.

The same scenario would happen if replacing UG400. These two scenarios are what gave people the impression that ACE2s are position-locked.

Replacing UF400 or UF500 would only work with vanilla ACE2s. Using an OTP-ed controller would result in an addressing conflict with either U5500 or UG400. Since vanilla ACE2s appear with frequency slightly more than 50%, this is what gave wildly different reports when replacing those. About half of technicians (the ones lucky enough to have installed a vanilla) would report no problem replacing them; while the other half (the unlucky who installed an OTP-ed) would say it didn't work.

Therefore, the consensus when replacing these ICs was that: the safest is to just replace them from same model, same position. This made the repair highly inefficient and very expensive: a complete board was often required, just to get one chip.

The procedure that follows, which seems complicated due to the level of abstraction, but is in fact quite easy to implement, rearranges the configuration resistors, when required, to prevent an I2C addressing conflict.

### III.2 Rule 1: Don't be an idiot.
When replacing ACE2 controllers, the obvious first rule is to use the same revision: if the defective ACE2 is a CD3217B13, do not use a CD3217B12 or a CD3218B12.

### III.3 Case 1: You have a donor board for the same device
If you have a donor board for the exact same device you are working on, then use the same controller (same position on the board), and it will work directly.

### III.4 Case 2: You do not have a donor board for the same device
It might be difficult to have donor boards for every device that one has to fix, be it only on the matter of price: donor boards for Pro / Max boards can cost in the 200USD ballpark, or even more if the device is recent. In this case, your replacement ACE2 should be a vanilla one. The procedure happens in two major steps.

#### III.4.1 Configuring the I2C addresses
  - First**: Determine the I2C addresses of the controller you are replacing. These can be found in the schematic, which will contain a map for all the I2C buses on the board.

As an example, the following tables reproduce the maps for the AP I2C0 bus on page 56, and the SMC I2C1 bus on page 57, for the A2442 (due to licensing issues, the original table cannot be posted):

| DEVICE | CARDS/REFDEF | 7-BIT | 8-BIT |
| --- | --- | --- | --- |
| ACE2 - 0 (DEBUG) | USB-C 0 | 0x38 | 0x70 |
| ACE2 - 1 (DEBUG) | USB-C 0 | 0x3F | 0x7E |
| ACE2 - 2 (DEBUG) | USB-C 1 | 0x3B | 0x76 |
| ACE2 - 3 (DEBUG) | USB-C 1 | 0x3A | 0x74 |
| ACE2 - 4 (DEBUG) | USB-C 0 | 0x6B | 0xD6 |

| DEVICE | CARDS/REFDEF | 7-BIT | 8-BIT |
| --- | --- | --- | --- |
| ACE2 - 0 (DEBUG) | USB-C 0 | 0x38 | 0x70 |
| ACE2 - 1 (DEBUG) | USB-C 0 | 0x3F | 0x7E |
| ACE2 - 2 (DEBUG) | USB-C 1 | 0x3B | 0x76 |
| ACE2 - 5 (DEBUG) | USB-C 1 | 0x3A | 0x74 |
| BANK 1 ALL CALL | USB-C 0 | 0x6B | 0xD6 |

Using this table and the names of the ACE2s on the board, you can determine that the addresses for the 4 controllers on the board are:

|  | UF400 UPC0 | UF500 UPC1 | UG400 UPC2 | U5500 UPC5 |
| --- | --- | --- | --- | --- |
| Port 1 | 0x38 111000b | 0x3F 111111b | 0x3B 111011b | 0x3A 111010b |
| Port 2 | 0x38 111000b | 0x3F 111111b | 0x3B 111011b | 0x3A 111010b |

  - Second:** Determine the addresses that your vanilla ACE2 will acquire once installed on the board, following the I2C Addresses Decoding paragraph above.

For example, on an A2442 board, after replacing U5500 by a vanilla CD3217, the computation has already been done above and the CD3217 will acquire addresses 0x3F and 0x2F.

  - Third:** Determine if the acquired addresses are the ones on the I2C maps in the schematics.  If there are differences, change the `ADDR`, `CNTL1` and `CNTL2` configuration so that the acquired addresses match the ones on the I2C map.

For example, on our A2442 board, after replacing U5500 by a vanilla CD3217, it will acquire addresses 0x3F = 111111b and 0x2F = 101111b. The schematic demands 0x3A = 111010b and 0x3A = 111010b for ports 1 and 2. You should thus:

- Set `ADDR` to 010, by connecting it to `GND` with an 84.5kΩ resistor. This can be achieved simply by installing that resistor in the position `R5650` which is NOSTUFF.
- Not touch `CNTL1`, which is already 1 since pulled to `PP3V3_UPC5_LDO`.
- Pull `CNTL2` to `PP3V3_UPC5_LDO`. This can be achieved by simply moving `R5508` to the position `R5610` which is NOSTUFF.

  - Fourth:** Connect the USB-C charger to a USB-C receptacle **different** from the one corresponding to the ACE2 you just worked on. If the board negotiates 20V, you did everything correctly. If it doesn't, then you either messed up the I2C configuration, or you damaged something in the process. In this case, start again.

  - Fifth:** Power up the board from the port corresponding to the controller you worked on. If the board negotiates 20V, you can put it back in the housing and test it in housing. If it doesn't, or if the test in-housing shows issues with charging the battery then you might have lingering issues, and you can move to the next section.

#### III.4.2 Fixing lingering issues.
Lingering issues are impossible to predict, because they depend on the internal firmware of ACE2 you used. The ACE2 is a complex chip, that has internal programming, customized for each board it is used on. You might be lucky and have used an ACE2 that is directly compatible with your board. Or you might be unlucky, and have picked one that was configured for another device.

So far, two types of lingering issues have been experienced:

##### III.4.2.1 No PD negotiation when the board is out of the housing, but it works and charges when the device is assembled and powered up
One instance of this issue has been [https://youtu.be/F4ZkKnm9CsU documented] on an A2442 which had UF400 replaced with a (vanilla) CD3217B12 from A2338 M1. The characteristic symptoms are, when the board alone is powered from the port corresponding to the CD3217B12 that has been replaced:

- The ACE2 outputs `LDO_3V3` and `LDO_CORE`.
- The ACE2 doesn't output `PP_HV`.
- The `BUSPOWER` pin is pulled to `GND`.

In this situation, the fix consists simply in pulling `BUSPOWER` to `LDO_3V3`.

##### III.4.2.2 No PD negotiation, whether the board is out or in housing.
One instance of this issue has been [https://youtu.be/3euAFgT3ec0 documented] on an A2442 which had UG400 replaced with a (vanilla) CD3217B12 from A2338 M1. The characteristic symptoms are, when the board alone is powered from the port corresponding to the CD3217B12 that has been replaced:

- The ACE2 outputs `LDO_3V3`, `LDO_CORE` and `PP_HV`.
- No `PPBUS_AON`.
- `CHGR_AUX_DET` is 0V.
- `CHGR_AUX_DET_3V3` is 3.3V.

In this situation, the fix consists simply in removing `RH008`.

## IV. Known-tested replacements
These are procedures that have been accomplished and tested to be successful. In each procedure, an ACE2 has been replaced, and it doesn't have to be mentioned: it is implicit that it has been done.

To those who want to contribute:

- Please only contribute if you are the one who performed it, and be as precise as possible, especially regarding the origin of the replacement ACE2.
- When adding a new section, for a device that has already been documented, please try to group it with already existing contributions for that device, to make searching easier.
- Testing should be done ideally on a previously working board. If the experience comes from a defective device, but didn't work, then it is not a good data point: indeed, we cannot be sure that the board has no other issues, or that your diagnosis was correct. Therefore, only post: negative experiences on originally working devices; or positive experiences.
- A replacement is considered successful if the Macbook can successfully go through a DFU Restore, and all USB-C functions are normal: charging, USB 2.0, USB3.x, Thunderbolt and display output.
- Macbooks only for now. We can consider merging data for Macbooks and iPads once we have determined a common methodology.

### A2442 (2021 M1 Pro / Max 14" Macbook Pro)
#### Replacing UG400.
The replacement ACE2 is a CD3217B12 coming from an A2338 M1 (regardless of position) and proceeds as follows:

Replace `RG201` by a 140kΩ resistor.

Move `RG409` to the `RG411` position (NOSTUFF).

Move `RG408` to the `RG412` position (NOSTUFF).

Lingering issue: No PD negociation, whether the board is in or out of housing. Fixed by removing `RH008`.

#### Replacing UF400 or UF500.
The replacement ACE2 is a CD3217B12 coming from an A2338 M1 (regardless of position). The procedure works almost right away, except for one lingering issue: the controller that has been replaced will only negociate PD and charge after the device has been turned on once, after a battery disconnect. The issue is very minor, and will be completely transparent to the owner of the device, since, once the device has been turned on, it will work normally until next time the battery is disconnected. Fixing this issue is super easy, barely an inconvenience: move `RF411` to `RF410` (NOSTUFF) if UF400 was replaced; move `RF511` to `RF510` (NOSTUFF) if UF500 was replaced.

#### Replacing U5500 on an A2442.
The replacement ACE2 is a CD3217B12 coming from an A2338 M1 (regardless of position) and proceeds as follows:

Install an 84.5kΩ resistor in place of `R5650` (NOSTUFF).

Move `R5508` to the `R5610` position (NOSTUFF).

No lingering issue.

### A2681 (2022 M2 13.6" Macbook Air)
#### Replacing UF400 or UF500.
The replacement ACE2 is a new CD3217B13 (Aliexpress). Works right away.

#### Replacing U5500.
The replacement ACE2 is a new CD3217B13 (Aliexpress) and proceeds as follows:

Install an 84.5kΩ resistor in place of `R5550` (NOSTUFF).

Move `R5508` to the `R5510` position (NOSTUFF).

## V. About the ROM
This information is sourced from the [https://www.ti.com/lit/ds/symlink/tps65982.pdf?ts=1758735586177&ref_url=https%253A%252F%252Fwww.mouser.co.uk%252F TPS65982 documentation]. Even though the ACE2 is not a TPS65982, everything indicates that large portions of this documentation apply to the ACE2.

The ACE2 controller has an internal boot code that gives it the first instructions to execute once powered on. These include setting up the I2C addresses, and probing the BUSPOWER pin to determine the behaviour to adopt in a dead-battery (or no-battery) condition. It then proceeds to execute its application code, which is located on an external SPI flash ROM, which we will simple call the ROM.

An ACE2 connected to the ROM is referred to as Master. An ACE2 that is not connected to a ROM is called a Slave, and downloads the application code from a Master through a UART bus. The ACE2 allows one Master to have up to 7 Slaves. Apple seems to design their boards with at most one Slave for each Master. Some 4-port boards will have a dual Master-Slave configuration; some will have a 4-Master configuration.

The replacement procedures that have been documented above do not require the ROM to be moved together with the ACE2, when sourcing from a donor, and there is absolutely no evidence that these two parts are paired together.

The ROM has its contents duplicated in two regions, as a failsafe in case one of the copies becomes corrupted, for example after a shutdown while it is being updated, as indicated on pages 72, 73 of the documentation. In case it determines the Application Code makes no sense, the ACE2 will automatically try to execute the backup. Thus it is extremely unlikely that the contents of the ROM becomes corrupted, as it would mean that both regions are defective. Of course, it is possible, but extremely unlikely.

There are no clear indications, when power sequencing ACE2 controllers, that it is unable to execute its Application Code. Thus, if one suspects a problem with the Application Code, the only solution is to either replace the ACE2 ROM with one coming from the same device, same position. Or try to flash it using, for example, a CH341a device. This requires, of course, having a correct dump for that particular position on the board. Be mindful that the ACE2 ROM is powered by 3.3V, so you will need a CH341a that has a voltage shifter.

Experience has shown that, each time there was a problem with an ACE2 ROM, the IC itself was defective, which was determined simply because the CH341a could not interface with it.

In other words, there has never been an instance where the IC could be read, re-flashed, and that solved the issue with the Macbook, which seems natural since the ACE2 ROM has a backup.
