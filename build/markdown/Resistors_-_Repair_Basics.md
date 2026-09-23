---
title: "Resistors - Repair Basics"
pageid: 146
revid: 14125
kind: explanatory_guide
source: "https://repair.wiki/w/Resistors_-_Repair_Basics"
history: "https://repair.wiki/index.php?title=Resistors_-_Repair_Basics&action=history"
permalink: "https://repair.wiki/index.php?oldid=14125"
last_edited: "2026-02-27T03:58:49Z"
contributors:
  - "Admin"
  - "ASRepairs"
  - "Phonograph Steve"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for Resistors"
  - "Missing device page"
  - "Repair Basics"
infobox:
  Device: "Resistors"
  Type: "Component"
  Difficulty: "1. Easy"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Resistors - Repair Basics

This article aims to provide a comprehensive overview of resistors from a repair perspective, detailing their function, types, common issues, testing methods, and replacement considerations.

## What is a Resistor?
![Resistor symbols commonly found in schematics (Figure 1)](images/9/9d/Resistor_symbols.jpg)A resistor is a fundamental electrical component found in most electronic circuits and devices. **Their characteristic property is electrical resistance, this is, resisting the passing of electrical current through them, without blocking it completely.**

The resistance of a resistor is measured in Ohms, and the symbol of this unit is the uppercase Omega (Ω) from the Greek alphabet.

Resistors are typically identified by the symbols shown in Figure 1 and are usually denoted with the letter R followed by an identifier number. (E.g., R381)

### Glossary of Basic Resistor Terminology
The terminology listed here will be helpful in understanding this article as well as technical literature and discussions elsewhere:

- **Resistance:** The "value" of a resistor, measured in Ohms (Ω). Its numerical value is the ratio between voltage and current in the resistor, which are physically related by Ohm's Law.
- **Ohm's Law:** The law of physics that relates the voltage (V) and current (I) through a resistor of a specific value (R): **V = I * R**

## Function
When a voltage is applied across a resistor, an electrical current will flow through it, which is restricted to a certain amount by its resistance in accordance with Ohm's law. This process dissipates electrical energy into heat.

Despite their very basic nature, resistors are used for a great variety of tasks, some common ones listed as follows:

#### Voltage Dropper / Current Limiter
A resistor is the most basic solution to cases where an electrical device needs to be powered from a source that produces a higher voltage than the device can use to function. A resistor is wired in series with the load, of a value calculated from the amount of volts it needs to get rid of, and how much current the device needs.

For example, a device that requires 3V at 1A needs to be powered from a 5V supply. To get 3 volts from 5 volts the series resistor R needs to drop 2 volts (5 - 3 = 2). Now we need to find a resistor that will let 1A pass through (the current the device needs) when 2 volts are put across it.

Ohm's law tells us that V = I*R. Plugging the numbers we got, we see that 2 [V] = 1 [A] * R [Ω], and solving for R gives us a value of 2 Ohms.

#### Voltage divider
A voltage divider is an electrical circuit that divides a higher input voltage into a lower output voltage using two or more resistors in series.

It is generally used to create a lower voltage that is proportional to a higher one from which it is powered, which can be a signal, or a voltage reference or supply. Another variety of uses is to create simple custom voltage sources from an existing supply, as can be necessary for biasing transistors.

The output voltage of a resistive divider is determined by the ratio of the resistance values in the circuit like so:
![Voltage divider circuit (Figure 2)](images/2/2c/Resistor_divider.png)
  - Voltage Divider formula (assuming NO LOAD on Vₒᵤₜ):**

<math>V_\mathrm{out} = \frac{R_2}{R_1+R_2} \cdot V_\mathrm{in}</math>

When the circuit is loaded, it is equivalent to an ideal voltage source supplying the unloaded voltage, with a series resistor of a value equal to R1 and R2 in parallel.

Uses:

- Reference Voltage: Voltage dividers can be used to create stable reference voltages for sensor calibration, analog signal processing, and feedback in voltage converters; provided they are powered from a stable voltage source, as any deviations in the source voltage will likewise appear in the scaled down output.
- Voltage Scaling: They can be used to scale down high input voltages to levels suitable for analog-to-digital converters (ADCs) or microcontrollers.
- Biasing Transistors: Voltage dividers set the base voltage of transistors in amplifier and switching circuits to ["bias"](wikipedia%3ABiasing.md) the voltage to a certain level.
- Voltage Monitoring: In some battery-powered devices, voltage dividers are used to monitor the battery voltage to determine its state of charge. This is a similar application to the aforementioned voltage scaling for measurements.
- Voltage Regulation: In some cases, voltage dividers are used in conjunction with other components to approximate voltage regulation in simple power supply circuits.
- Volume control in analog audio: for this, a potentiometer is used, to have an adjustable ratio in the divider and thus making the volume user-adjustable.
- Et Cetera.

#### Resistor sensors
Resistor sensors, also known as resistive sensors, are a class of sensors that rely on changes in resistance to detect and measure various physical phenomena, such as temperature or light. Examples of such sensors include thermistors and photoresistors.

#### Pull-up / Pull-down
Pull-up and pull-down resistors are commonly used in digital electronics to ensure that a digital input signal is in a known state when it's not actively being driven by an external source. They are essential for preventing floating or undefined states.

A pull-up resistor connects a digital input to a "high" voltage level (usually Vcc, which is the supply voltage). This effectively "pulls up" the input to a logical HIGH state when the switch or sensor is not actively grounding it. Pull-up resistors are often used with switches and sensors that are normally open. When the switch is closed or the sensor is active, it grounds the input, causing it to read as LOW. When the switch is open or the sensor is inactive, the pull-up resistor ensures the input reads as HIGH.

A pull-down resistor connects a digital input to ground (GND). This "pulls down" the input to a logical LOW state when the switch or sensor is not actively driving it HIGH. Pull-down resistors are typically employed with switches and sensors that are normally closed. When the switch is open or the sensor is inactive, it keeps the input grounded (LOW). When the switch is closed or the sensor is active, it drives the input HIGH.

Usually, pullup or pulldown resistors are 2.2k to 10k ohms.

#### Current measurement
Current measurement using shunt resistors is a widely used method in electronics and electrical engineering to accurately measure the current flowing through a circuit.

The principle behind this technique is Ohm's Law <math>V = I * R</math>

A low resistance, precise "Shunt" resistor is used in series with the rest of the circuit "load" to measure the current flowing in said circuit by measuring the voltage drop across the shunt. In some cases, the voltage drop is very tiny and needs to be amplified using [Op-Amps](Repair_Basics_-_Operational_Amplifiers_%28Op-Amps%29.md). In modern electronics, specialized Integrated Circuits "ICs" are used to measure the voltage drop/current draw.

The shunt resistor is specifically designed with a known and well-calibrated resistance value, very close to 0 Ohms, usually 0.002.

Usually, the shunt resistor is placed where a fuse might be, where all the current passes through it. Sometimes, the shunt resistor itself acts as a fuse if a short circuit happens since it will be the highest resistance point in the circuit.

[https://www.researchgate.net/figure/Current-measurement-with-a-shunt-resistor-and-low-pass-filteradapted-from-14_fig2_221045514 Example and further reading]

## Resistor Packages and Value Codes
Resistors of different types take on a variety of different shapes or "packages", which use a variety of codes to mark the resistor value. Some of the common ones are as follows:

### Axial Through-Hole Resistor
Historically the most common form factor, still common today but it has been greatly displaced by surface mount types.

These have an elongated cylindrical shape (often narrower around the middle and rounded at the ends, giving them a "peanut" shape) with a wire coming out of each end.

They most often use a color code made of four or five colored bands around their side. Occasionally they will have their value printed on plain numbers.

### Surface Mount Device (SMD)
These resistors  [https://www.newmatik.com/knowledge-base/KB-EN-00928/resistor-case-sizes come in different sizes] but are usually small in size and have no wire leads, instead their metallized ends get soldered directly to pads on a circuit board.

Appearance wise, they are small rectangular and thin wafers, black on top with a white ceramic substrate underneath, and a three or four digit numerical code denoting the value, where the last digit is the multiplier or "number of zeroes" (for example, 221 on a resistor means 220 ohms).

Another notation has the value written as a number with decimals, where the decimal point is replaced with a letter that represents the multiplier (R for 1, K for 1000, M for 100000), for example, "4k7" denotes a 4700 Ohm resistor. Sometimes the letter will be at the beginning or the end, indicating there would be a zero on the unused side. For example, K33 for a 330 Ohm resistor, or 10R for a 10 Ohm one.

This notation is also occasionally used in power resistors of the through-hole axial and ceramic types.

[https://www.digikey.com/en/resources/conversion-calculators/conversion-calculator-smd-resistor-code Here is an online calculator]  for the 3 widely used standards.

## Types
![Different types of resistors (Figure 3)](images/a/ac/Resistor_types.png)

### Wire Wound Resistor
One of the oldest types of resistors and still widely used for power applications. They are made of a length of metal wire coiled around a rigid insulating core for support or potted in a porcelain shell with cement.

The wire is usually Nichrome for its high temperature resistance, and the cores are usually made of some form of ceramic, mica or rarely glass for the same reason. Some antique resistors contained asbestos in the core.

Of the ceramic core types, most have the core covered in glaze, encasing the windings. Sometimes the glaze would leave a strip of uncoated windings along the length of the resistor, in order for a clamp to be attached and make contact at a desirable location, making a tapped resistor. The core itself is hollow to allow a bolt to pass through for fastening.

Some other examples leave the windings uncovered, usually in older high power resistors and rheostats.

Their most common use is as power resistors, and as heating elements. Some high precision resistors for instruments are also wire wound, sometimes with two different thicknesses of wire to trim the value to spec. These sometimes lack the construction meant to withstand high temperatures.

Because of their construction, they can have substantial parasitic inductance, making them unsuitable for high frequency applications. They can also introduce RF noise to a circuit, acting as loop antennas.

### Metal Film Resistor
Made by depositing a microscopically thin layer of metal on a ceramic substrate, and sometimes with a spiral pattern etched to make something akin to a wirewound resistor. This can give them similar issues with inductance but to a much lesser degree.

### Carbon Composite Resistors
They were the most common in electronics around the middle of the 20th century, and are made of a slug of a graphite-infused composite material, with leads at each end and encased in bakelite. Many have drifted susbtantially in value over the decades.

They most often use the colored bands code, with some examples having only 3 bands, lacking the tolerance band.

One of their advantages was having very low parasitic inductance.

### Variable resistors
#### Potentiometers
These can be adjusted to change the resistance value, usually with a knob or a screw.

They find applications in volume controls, dimmer switches, and tuning circuits.

#### Thermistors
Thermistors are designed to exhibit a predictable change in resistance in response to changes in temperature, which makes them useful in a wide range of applications, especially in temperature-sensing and temperature-compensation circuits.

There are two common types of thermistors:

#### Negative Temperature Coefficient (NTC)
- NTC thermistors are the most common type. As the temperature increases, their resistance decreases, hence the term "negative temperature coefficient."
- The resistance-temperature relationship of NTC thermistors is nonlinear, meaning that the change in resistance is more significant at some temperature ranges than others.
- NTC thermistors are often used in temperature sensors and temperature compensation circuits or protection circuits. For example, they are found in thermostats, thermometers, and devices that require temperature control.

#### Positive Temperature Coefficient (PTC)
- PTC thermistors exhibit an increase in resistance as the temperature rises, hence the term "positive temperature coefficient."
- The resistance-temperature relationship for PTC thermistors is also nonlinear.
- **PTC thermistors can be used as self-resetting fuses or current limiters. When they heat up due to excessive current, their resistance increases, reducing the current flow.**

#### Varistors
A varistor, despite often being considered a type of resistor, is actually a semiconductor device with a behavior similar to a pair of zener diodes wired in anti-series (in series but in opposite directions). This effectively means that the varistor is non conductive in either direction up to a specific threshold voltage (positive or negative), where it suddenly starts conducing and clamps down the voltage to this limit.

They are used to protect electrical circuits and devices from voltage spikes or transient overvoltage conditions. Varistors are also known as voltage-dependent resistors (VDRs) because their electrical resistance changes with the applied voltage. They are commonly used in various electronic and electrical systems to absorb and dissipate excess voltage, preventing damage to sensitive components.

Modern varistors, called Metal Oxide Varistors, are made by sintering oxidized metal granules into pellets in a controlled manner, the metal oxide forms effectively a mass of randomly oriented, microscopic diodes which end up forming series chains by mere chance; hence the non polarized behavior with a diode-like threshold voltage.

Historical varistors were made by connecting two copper oxide or selenium rectifiers in antiparallel, and were mostly used to protect telephone lines and receivers.

#### Photoresistors
Also known as Light Dependent Resistors (LDRs), these exhibit changes in resistance based on the intensity of light falling on them. They are used in light-sensitive applications. They are usually small, though large ones are used in applications such as light-sensing streetlight switches, where they drive a thermal relay dirctly.![Measuring a Resistor (Figure 4)](images/1/1d/Resistor_measurement_mm.png)

## Testing a Resistor
  - Make sure the resistor does not have any physical damage such as liquid damage/corrosion first! That's the quickest way of identifying a faulty resistor.**

Once you have identified the resistor and its specified resistance, you can accurately measure its resistance using a multimeter, as depicted in Figure 4.

  - It's important to note that when measuring a resistor, polarity is not a concern.**

Ideally, you should measure the resistor outside of the circuit.
- When measuring a resistor within a circuit, the measured value will always be either equal to the ideal resistance or lower. If you happen to measure a resistance higher than the ideal value, this indicates a faulty resistor.
  - The reason the resistance of a resistor within a circuit is lower than its ideal value is because you are effectively measuring not only that specific resistor but also everything else connected to it in parallel. **When resistors are connected in parallel, they collectively reduce the overall resistance.**
Resistors typically fail in an "open" state, which means they will exhibit a significantly higher resistance than normal or even an open circuit. This is often a result of excessive current causing them to overheat.

Rarely, resistors might exhibit a **Value Drift.** Over time, a resistor's resistance value might change due to environmental factors or aging.
![Wirewound Resistor (Figure 5)](images/a/ad/Wirewound_resistor.png)
If the original resistance is **unknown**, you need to compare with a working device or look up a schematic.

On THT wire-wound resistors, it is still possible to determine the resistance even if the markings have worn off or got damaged. To do this, scratch the surface of the resistor in the middle to expose the resistive wire underneath. Then, use a multimeter to measure the resistance from the middle to both ends of the exposed wire. One of the ends will register half of the original resistance, while the other will show an "OL" reading, indicating an open circuit. This method works because when these resistors fail, a break or "cut" occurs somewhere in the resistive wire. That cut can be only in one of the halves.

## Replacement Considerations
The most important things to keep in mind when replacing a faulty resistor are as follows:

1. **Resistance:** Choose a replacement resistor with the same resistance value as the faulty one. Keep in mind that there are different tolerances (1,5,10, or 20 percent). Try to stick to 1% if possible.
1. **Power rating:** Ensure the replacement resistor can handle the same or higher power as the original. If you're unsure of the original resistor's power rating, opt for the highest-rated resistor available in a similar size.
1. **Package size:** Try to choose a replacement resistor with the same dimensions as the faulty one. If this isn't available and size constraints are not an issue, you can opt for a larger or smaller resistor as long as it matches the power rating, as this will function the exact same way.
