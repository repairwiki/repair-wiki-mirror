---
title: "Inductors - Repair Basics"
pageid: 522
revid: 4378
kind: explanatory_guide
source: "https://repair.wiki/w/Inductors_-_Repair_Basics"
history: "https://repair.wiki/index.php?title=Inductors_-_Repair_Basics&action=history"
permalink: "https://repair.wiki/index.php?oldid=4378"
last_edited: "2024-07-17T14:28:19Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for Inductors"
  - "Missing device page"
  - "Repair Basics"
infobox:
  Device: "Inductors"
  Type: "Component"
  Difficulty: "1. Easy"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Inductors - Repair Basics

This article aims to provide a comprehensive overview of inductors from a repair perspective, detailing their function, types, common issues, testing methods, and replacement considerations.
![Inductor schematic symbol and common packages (Figure 1)](images/6/68/Inductor_types.png)

## What is an Inductor?
An inductor is an essential passive electronic component that **stores energy in a magnetic field when an electric current flows through it**. Inductors resist changes in current flow and are widely used in various electronic circuits.

Inductors are measured in "Henry" but a Henry is a large unit so you'll typically find them in milli-Henry "mH", nano-Henry "nH", or micro-Henry "uH"

In essence, ***an inductor consists of a wire coiled around a core***, with the choice of core material and the number of turns influencing its inductance and magnetic field strength.

Inductors are typically identified by the symbol shown in Figure 1 and are usually denoted with the letter L followed by an identifier number. (E.g., L3)

### Function
Inductors serve various functions in electronic circuits, including:

#### Voltage Smoothing
Inductors in the output stage of voltage converter circuits serve to filter and stabilize the output voltage. By smoothing the pulsating DC output, inductors reduce voltage ripples, contributing to a stable and continuous power supply. **In almost every device that has DC-DC voltage converters you will most likely find an inductor at the output.**

#### Energy Storage
Inductors store energy in their magnetic fields, and this property is crucial in applications like boost and buck voltage converters, which are essential in power supplies and voltage regulators.

#### Electro-magnet
When an electric current flows through the coil, it generates a magnetic field, turning the inductor into a temporary magnet. This principle finds practical application in relays, where an inductor serves as the electromagnet to control the switch mechanism.

#### Filtering
Inductors are used in conjunction with [capacitors](Capacitors_-_Repair_Basics.md) to create low-pass and high-pass filters (LC Filters), allowing certain frequencies to pass while attenuating others. By themselves, Inductors block AC, and let DC pass through.

#### Resonance Circuits
Inductors are crucial in [resonance circuits](wikipedia%3ALC_circuit.md), where they interact with [capacitors](Capacitors_-_Repair_Basics.md) to establish resonance at a specific frequency. In series resonance, inductors limit current increase, while in parallel resonance, they contribute to maintaining a high impedance at the resonant frequency. The strategic use of inductors in resonance circuits is fundamental for designing efficient filters, antennas, and oscillators in electronic systems.

#### Inductive Sensing
Inductors are used in sensors for inductive sensing applications, such as proximity sensors and metal detectors, where changes in inductance are used to detect the presence or absence of certain materials.

### Types
#### Air Core Inductors
Air core inductors have a coil wound around a non-magnetic form, such as plastic or ceramic. They are used in radio-frequency applications and where magnetic interference must be minimized.

#### Iron Core Inductors
Iron core inductors have a coil wound around a magnetic core, typically made of iron or other magnetic materials. They are used in power applications and [transformers](Transformers_-_Repair_Basics.md).

#### Ferrite Core Inductors
Ferrite core inductors use a core made of ferrite, a ceramic material with high magnetic permeability. They are common in high-frequency applications and EMI suppression.

#### Toroidal Inductors
Toroidal inductors have a coil wound around a ring-shaped core. They offer high inductance and are often used where compact size and low magnetic interference are critical.
![Measuring an Inductor (Figure 2)](images/7/7f/Inductor_measurement.jpg)

## Testing an Inductor
Make sure the inductor does not have any physical damage first! That's the quickest way of identifying a faulty inductor.

To measure an inductor, use a digital multimeter and check for continuity. **Remember, an inductor is just a wire!**

- Set your multimeter to resistance mode.
- Connect the multimeter's leads across the inductor
- The multimeter should display around 1 Ohm since the inductor is just a wire.
  - If you measure high resistance or OL that means the inductor is blown open.

The inductor is **the most reliable electrical component.** If you find a damaged inductor, *that means it is a symptom and not the cause and you most likely have a short circuit somewhere.* [How to find short circuits?](Short_Circuits_-_Repair_Basics.md)

If an inductor fails, it most likely fails in a "blown open" way. Caused by excessive flow of current, leading to overheating and subsequent failure.

You can also use an LCR meter to measure the inductance the same way but it is usually not necessary.

## Replacement Considerations
When replacing an inductor, consider the following factors:

1. **Inductance Value:** Choose a replacement inductor with the same or very close inductance value to the faulty inductor.
1. **Current Rating:** Ensure the replacement inductor can handle the same or higher current than the original, especially in power applications.
1. **Type of Core:** Match the type of core (air core, iron core, ferrite core, etc.) to the original inductor, as it can affect the inductor's performance.
1. **Physical Size:** Choose a replacement with a similar or compatible physical size.

Replacing an inductor with the wrong specifications can lead to it breaking again.
