---
title: "How to Read Resistor, Capacitor and Transistor Codes: A Beginner's Guide"
slug: how-to-read-resistor-capacitor-transistor-codes
category: Learn the Basics
target_audience: Students and beginners learning to identify component values and part numbers
meta_description: "Learn to read resistor colour bands, SMD resistor codes, capacitor codes like 104 and 473, electrolytic markings, and transistor and diode part numbers, with worked examples."
---

# How to Read Resistor, Capacitor and Transistor Codes: A Beginner's Guide

Every component carries a code that tells you what it is. Learning to read these codes saves time at the workbench and prevents wrong purchases. This guide covers the most common ones: resistor colour bands, SMD codes, capacitor numbers, and transistor and diode part numbers.

If the difference between component types is new to you, start with [passive vs active components](guide.html?slug=passive-vs-active-components-guide#passive-vs-active-components-guide).

## Part 1: Resistor Colour Bands

Through-hole resistors use coloured bands. Hold the resistor with the tolerance band (gold or silver, usually set apart) on the right and read from the left.

**Digit colours**
- Black = 0
- Brown = 1
- Red = 2
- Orange = 3
- Yellow = 4
- Green = 5
- Blue = 6
- Violet = 7
- Grey = 8
- White = 9

**4-band resistors:** the first two bands are digits, the third is the multiplier (number of zeros), and the fourth is tolerance.

**5-band resistors:** the first three bands are digits, the fourth is the multiplier, and the fifth is tolerance. These are common for 1% precision parts.

**Tolerance colours:** Brown = ±1%, Red = ±2%, Gold = ±5%, Silver = ±10%.

**Special multipliers:** Gold = ×0.1 and Silver = ×0.01.

**Worked examples**
- Brown, Black, Red, Gold = 1, 0, ×100 = **1,000Ω (1kΩ) ±5%**
- Yellow, Violet, Orange, Gold = 4, 7, ×1,000 = **47kΩ ±5%**
- Brown, Black, Black, Red, Brown = 1, 0, 0, ×100 = **10kΩ ±1%**

When in doubt, confirm the value with a multimeter.

## Part 2: SMD Resistor Codes

Surface-mount resistors print numbers instead of colours.

- **3 digits (for example 103):** first two digits, then the number of zeros. 103 = 10 followed by three zeros = **10kΩ**. 472 = 4.7kΩ.
- **4 digits (for example 1002):** first three digits, then the number of zeros. 1002 = **10kΩ** (a 1% part).
- **Letter R marks a decimal point:** 4R7 = 4.7Ω, and R22 = 0.22Ω.
- **000 or 0** means a zero-ohm link.

## Part 3: Capacitor Codes

**Ceramic and film capacitors** use a three-digit code in picofarads (pF), read like SMD resistors.

- **104** = 10 followed by four zeros = 100,000pF = **100nF (0.1µF)**
- **103** = 10,000pF = **10nF**
- **102** = 1,000pF = **1nF**
- **473** = 47,000pF = **47nF**
- **224** = 220,000pF = **220nF**
- **22** or **220** with no third digit often means a direct pF value, such as 22pF

A letter after the number gives the tolerance: **J** = ±5%, **K** = ±10%, **M** = ±20%. A voltage such as 50V or 63V may also be printed, and you should never run a capacitor above its rated voltage.

**Electrolytic capacitors** print the value and voltage directly, for example 100µF 25V.
- A **stripe on the can** marks the negative leg.
- The **longer leg** on a new part is positive.
- Reversing polarity or exceeding the voltage can make it fail or vent, so always check before powering up.

**Quick rule:** use a capacitor with a voltage rating well above the circuit's working voltage. Many designs use a rating at least 1.5 to 2 times higher.

## Part 4: Transistor and Diode Part Numbers

The prefix tells you where the number system comes from.

- **BC, BD, BF** (for example BC547, BD139): European (Pro Electron) numbering. BC is a small-signal transistor and BD is a medium-power one.
- **2N** (for example 2N2222, 2N3055): US (JEDEC) numbering.
- **2SA, 2SB, 2SC, 2SD** (for example 2SC945, 2SD882): Japanese (JIS) numbering. A and B are PNP, while C and D are NPN.
- **1N** (for example 1N4007, 1N4148, 1N5819): diodes. The 1N4007 is a general rectifier (1A, 1000V), the 1N4148 is a small-signal diode, and the 1N5819 is a Schottky diode.

**Identifying pins**
Transistor pinouts are not the same across all types, even in the same package. For example, a BC547 and a 2N2222 in a TO-92 package may have different pin orders. **Always check the datasheet** before connecting a transistor.

**Diode polarity:** the **band** on a diode marks the cathode. Current flows from the anode (no band) to the cathode (banded end).

## Part 5: Other Common Markings

- **Inductors** often use the same three-digit code in µH, for example 101 = 100µH.
- **IC markings** include the part number, manufacturer logo and date code. A date code like 2415 usually means year 24, week 15.
- **LEDs** are usually identified by colour and size, and by the longer leg being the anode.

## A Simple Habit That Helps

Keep a small card with the colour code and the capacitor codes at your bench until you remember them. Then confirm uncertain parts with a multimeter or a capacitance meter.

---

*Aakash Electronics stocks resistors, capacitors, diodes and transistors across a wide range of values and part numbers. [Search our parts list](/products) or visit the SP Road counter and we will help you identify any part.*
