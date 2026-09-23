---
title: "Transistors - Repair Basics"
pageid: 234
revid: 14022
kind: explanatory_guide
source: "https://repair.wiki/w/Transistors_-_Repair_Basics"
history: "https://repair.wiki/index.php?title=Transistors_-_Repair_Basics&action=history"
permalink: "https://repair.wiki/index.php?oldid=14022"
last_edited: "2026-02-19T17:13:26Z"
contributors:
  - "ASRepairs"
  - "Phonograph Steve"
anonymous_edits: 1
categories:
  - "Explanatory guide"
  - "Explanatory guides for Transistors"
  - "Missing device page"
  - "Repair Basics"
  - "Stubs"
infobox:
  Device: "Transistors"
  Type: "Component"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Transistors - Repair Basics

This article aims to provide a comprehensive overview of transistors from a repair perspective, detailing their function, types, common issues, testing methods, and replacement considerations.
![Transistor symbols commonly found in schematics (Figure 1)](images/f/fb/Transistor_schematic_symbols.jpg)

## What is a Transistor?
A transistor is a crucial semiconductor device in electronics that **amplifies or switches electronic signals**. Transistors come in various types, and each type serves a specific purpose in electronic circuits.

There are many types of transistors, with the main ones being: Bipolar Junction Transistors (BJTs), Field-Effect Transistors (FETs), Isolated Gate Bipolar Transistors (IGBTs) and Phototransistors.

Transistors are typically identified by the symbols shown in Figure 1 and are usually denoted with the letter Q followed by an identifier number. (E.g., Q27). Discrete individual transistors come in plastic or metal packages with three or sometimes four terminals.

### Function
Transistors serve various functions in electronic circuits, including:

#### Amplification
Transistors amplify weak electronic signals to higher levels. This is essential in audio amplifiers, signal processing, and more.

#### Switching
Transistors can be used as electronic switches to control the flow of current in a circuit. They are used in digital logic circuits, microcontrollers, Power manager circuits, and more.

#### Voltage Regulation
A transistor may be used as a linear voltage regulator by dropping excess voltage from a source across itself, when controlled by a voltage reference, to produce a lower, stabilized voltage.

In switch mode power supplies, transistors are used for power conversion by rapidly switching on and off to either boost or step down the voltage depending on the circuit. By controlling the timing of their switching, voltage regulation can be achieved at the output.

#### Motor Control
Transistors, especially power IGBTs, are used in motor control circuits to drive and control the speed of 3 phase electric motors in appliances, robotics, and industrial equipment.
![Some transistor packages and types (Figure 2)](images/3/3d/Transistor_types_packages.png)

### Types
#### Bipolar Junction Transistors (BJTs)
BJTs come in two types:

##### NPN
An NPN transistor has three layers: the collector, base, and emitter. It allows current to flow from the collector to the emitter when a small current is applied to the base. NPN transistors are commonly used in amplification circuits.

##### PNP
A PNP transistor operates similarly to an NPN transistor, but the direction of current flow is reversed. Current flows from the emitter to the collector when a small current is pulled from the base. PNP transistors are also used for amplification and switching though they have become uncommon.

PNP transistors are particulrly common in older devices using Germanium transistors, made in the 1950's through the 1970's.

#### Field-Effect Transistors (FETs)
FETs are classified into JFETs (Junction Field-Effect Transistors) and MOSFETs (Metal-Oxide-Semiconductor Field-Effect Transistors), they both work in a similar way and both come in two types:

##### N-Channel
N-Channel FETs acts as an electronic switch between the drain and source when the gate is positively charged in relation to the source. The gate-to-source effectively forms a small capacitor, and the magnitude of current between the drain and source is directly linked to the charge on the gate. Consequently, unless the gate is actively discharged, the N-Channel FETs will remain in a conducting state. **No current flows from the gate to source.**

##### P-Channel
Works in opposite way to N-Channel, P-Channel FETs also act as an electronic switch between the drain and source but when the gate is **negatively** charged in relation to the source. The gate-to-source effectively forms a small capacitor, and the magnitude of current between the drain and source is directly linked to the negative charge on the gate. Consequently, unless the gate is actively being charged, the N-Channel FETs will remain in a conducting state. **No current flows from the source to gate.**

#### Insulated Gate Bipolar Transistors (IGBTs)
IGBTs combine the characteristics of BJTs and MOSFETs. They are used in high-voltage, high-current switching applications like inverter drives and power inverters. Current flows from the collector to the emitter if the gate is positively charged in relation to the emitter. Same case with the FET, if the gate is not being discharged, the IGBT will stay conducting until the gate is discharged.

Internally, IGBTs are high power bipolar transistors driven by a built in MOSFET.

#### Phototransistors
Phototransistors are bipolar junction transistors housed in translucent packages, allowing incident light to shine onto the internal transistor chip. BJTs are naturally light sensitive, but for most applications this effect is unwanted and the transistor is housed in an opaque package.

Due to the photoelectric effect, shining light onto the transistor chip has the same effect as passing current through the base of the transistor, making it conduct. The base is thus often left disconnected, making a two pin transistor, though in some cases it is made available. This allows for biasing the transistor or attaching a base discharging resistor, which increases it's speed response.

They are used as light detectors, being more sensitive than photodiodes due to their internal gain, but are much slower in response.

They are used inside optocouplers paired with LEDs in order to transmit signals between two parts of a circuit while keeping them electrically isolated.

Paired with LEDs too, they are used in optical tripwire sensors and encoders in electronic devices that require precise tracking of movement, such as printers.

Also they see use as the receivers in fiber optic media, and the receivers for infrared remote controls. The latter are often encased in black resin that is opaque to visible light, but transparent to infrared light.

## Testing a Transistor
Transistor testing methods depend greatly on the type of transistor and the failure modes trying to identify. A visual inspection should always be the first step. Some clear signs of likely deterioration or failure are listed as follows:

- Corrosion of the pins and metal shell (when applicable).
- Broken pins due to corrosion or mechanical fatigue from prolonged vibration.
- Discoloration of the transistor, the surrounding circuit or adjacent components, indicating overheating.
- Burn marks, holes and cracks on the transistor package.

Usually, transistors fail in a short circuit where some or all the pins are shorted together. In such instances, it may be necessary to inspect the rest of the circuit, both to find other components that may have been damaged by this short circuit, or failed components that may have caused the transistor to short in the first place.

Old metal package transistors may develop shorts as a result of the growth of [tin whiskers](wikipedia%3AWhisker_%28metallurgy%29.md) inside the shell.

Transistors may also fail open on occasion, often caused by the breaking of internal bond wires due to overcurrent or fatigue. Degradation of the semiconductor due to age, or the intrusion of air or moisture can cause transistors to develop resistive leakages between its electrodes.

### BJTs
The most basic test for a BJT is to check that the internal [PN junctions](PN_Junction_-_Repair_Basics.md) are in good shape. Essentially, a BJT should test as two diodes with a common terminal like is shown on Figure 1. Failing this test is a good indication of transistor failure, but a transistor may still have other issues (such as emitter-collector leakage or short) even if the diode junctions test normally.
1. Identify the transistor's pins and determine which is the base, emitter and collector.
1. * If the pinout can't be found from documentation or inferred from the surrounding circuitry, it may be determined by probing different combinations of pins with the multimeter in diode mode, trying to find one of the two configurations shown on Figure 1. This can also clarify if the transistor is PNP or NPN.  If the transistor has failed, it may not be entirely possible to find the pinout using this method.
1. * Transistors with metal shells often have a tab or a painted dot near the emitter, with the base being the closest pin to the emitter.
1. * It should be noted that some power BJTs have built in flyback diodes between the emitter and collector too.
1. Test for shorts or leakage: Set the multimeter to the highest resistance scale (or autoscale).
1. * Measure the resistance between the collector (C) and the emitter (E). If you measure below 100 Ohms that means the BJT is shorted. You might find values in the tens of kilo ohms to mega ohms, which indicate a leaky transistor but don't necessarily imply the transistor is unusable (this depends on the circuit it's used in).
1. * Measuring this value with the probes reversed may point you towards the presence of an internal flyback diode if you find a low value in one direction and and a high value in the opposite direction.
1. Test the internal junctions of the transistor: set your multimeter to diode mode.
1. * For an NPN transistor: Connect the red probe to the base (B) and probe the emitter and collector with the black probe. In both cases the multimeter should read a diode drop (typically 0.6 - 0.7 V or 0.2 - 0.5 V for old Germanium transistors).
1. * For a PNP transistor, repeat the same but reverse the meter probes (black on base), you should read the same diode values.
1. * If you measure a voltage drop that is substantially higher or lower or "OL" this means the transistor is faulty.

### FETs
You can verify the functionality of the FETs by charging or discharging the gate (G), which causes the drain (D) and source (S) to become conducting. This can be tested using a multimeter on diode mode.
1. Identify the transistor's pins and determine which is the gate, drain and source.
1. Firstly, make sure the FET is not shorted, measure the resistance between the drain (D) and the source (S). If you measure below 100 Ohms that means the FET is shorted.
1. If the FET is not shorted, set your multimeter to diode mode.
1. For N-Channel FETs, connect the red probe to the gate (G) and the black probe to the source (S).
1. Quickly switch the red probe to drain (D), you should measure a very very low voltage drop (close to 0) confirming the operation of the FET.
1. For P-Channel FETs, repeat the same but reverse the meter probes (black on gate), you should read the same diode values.
1. If you read a high voltage drop or "OL" that means the FET is faulty.

Alternatively, you can measure the capacitance of the gate (G) against the source (S) if you have access to and LCR meter. Value should be compared to the datasheet or a similar FET.

### IGBTs
1. Identify the transistor's pins and determine which is the gate, emitter and collector.
1. Set your multimeter to diode mode.
1. Usually, IGBTs come with a diode connected in reverse parallel "freewheeling diode" (figure 1) to allow current to pass in the other direction. This means that all you have to do to measure an IGBT is check if the diode is still functional.
1. Place the red probe on the emitter (E) and black probe on collector (C), you should measure a diode voltage drop (typically 0.4 - 0.7 V).
1. If you read a high or low voltage drop, or "OL" that means the IGBT is faulty.

If you have access to a LCR meter, measure the gate (G) capacitance against the emitter (E). Value should be compared to the datasheet or a similar IGBT.

## Replacement Considerations
If you can't replace the transistor with the exact same one, it is possible to use a different one while considering the following factors for each type. **Regardless, MAKE SURE THE PIN OUT MATCHES! If not, you most likely will kill everything connected to it!.**

### BJTs
1. **BJT type:** Ensure you select the correct type (NPN or PNP) based on the original transistor's function.
1. **Package Type:** Choose a replacement transistor with a compatible package type and pinout.
1. **Voltage and Current Ratings:** "VCE" and "IC". Match or exceed the voltage and current ratings of the replacement transistor to the original to avoid overloading the transistor.
1. **Gain:** In amplification applications, closely match the gain (hFE) of the replacement transistor to the original for proper amplification.
1. **Power Dissipation:** Ensure the replacement transistor can handle the same or higher power dissipation as the original.

### FETs
1. **FET type:** Ensure you select the correct type (N or P channel) based on the original transistor's function.
1. **Package Type:** Choose a replacement transistor with a compatible package type and pinout.
1. **Voltage and Current Ratings:** "VDS" and "ID". Match or exceed the voltage and current ratings of the replacement transistor to the original to avoid overloading the transistor.
1. **RDSon:** Resistance when turned on, It is very important to pick a FET that has the same or **lower** on resistance.
1. **Gate Capacitance:** Try to stick to a FET with a close gate charge to the faulty one.
1. **Switching Characteristics:** Pay attention to "Turn On/Off Delay Time" and "Rise/Fall Time" especially for sensitive switching applications.
1. **Power Dissipation:** Ensure the replacement transistor can handle the same or higher power dissipation as the original.

### IGBT
1. **Package Type:** Choose a replacement transistor with a compatible package type and pinout.
1. **Voltage and Current Ratings:** "VDS" and "ID". Match or exceed the voltage and current ratings of the replacement transistor to the original to avoid overloading the transistor.
1. **RDSon:** Resistance when turned on, It is very important to pick a FET that has the same or **lower** on resistance.
1. **Gate Capacitance:** Try to stick to a FET with a close gate charge to the faulty one.
1. **Switching Characteristics:** Pay attention to "Turn On/Off Delay Time" and "Rise/Fall Time" especially for sensitive switching applications.
1. **Power Dissipation:** Ensure the replacement transistor can handle the same or higher power dissipation as the original.

Replacing a transistor with the wrong specifications can lead to circuit damage! It's essential to choose a replacement carefully.
