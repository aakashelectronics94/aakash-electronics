---
title: "Choosing a Voltage Regulator: 7805 vs LM317 vs LDO vs Buck Converter"
slug: choosing-voltage-regulator-7805-lm317-buck-converter
category: Choosing Components
target_audience: Students, hobbyists, and engineers selecting a way to power circuits from a battery or adaptor
meta_description: "How to choose between a 7805, LM317, LDO regulator, and buck converter: heat, efficiency, dropout, current limits, and worked examples for 5V and 3.3V circuits."
---

# Choosing a Voltage Regulator: 7805 vs LM317 vs LDO vs Buck Converter

Most circuits need a steady voltage, and the supply you have is rarely the voltage you need. A 12V adaptor feeds a 5V Arduino. A battery drops as it drains. A voltage regulator solves this, but there are several kinds, and choosing the wrong one can mean a hot, wasted or damaged circuit.

This guide explains the main options and how to choose.

## Two Families: Linear and Switching

**Linear regulators** (7805, LM317, AMS1117) are simple and quiet. They burn off the extra voltage as **heat**.

**Switching regulators** (buck, boost converters) are more efficient because they rapidly switch and store energy, so they waste much less as heat. They are slightly more complex and can add some electrical noise.

## The Key Formula for Linear Regulators

The heat a linear regulator must dissipate is:

**Power lost = (Input voltage - Output voltage) x Current**

Example: a 7805 dropping 12V to 5V at 500mA loses (12 - 5) x 0.5 = **3.5W** as heat. That is too much for the bare part and needs a heat sink. The same 12V to 5V job at 100mA loses only 0.7W.

If the answer is more than about 1W, consider a heat sink or a switching regulator.

## The 7805 (and the 78xx family)

- Fixed **5V output**, up to about **1A** with a heat sink
- Needs an input of roughly **7V or more** (it needs around 2V of headroom, called dropout)
- The 7812 gives 12V and the 7809 gives 9V in the same way
- Add small capacitors on the input and output for stability (the datasheet suggests values)

**Good for:** simple 5V circuits, learning projects and low-current loads where a 9V or 12V supply is available.

**Not good for:** battery projects with a small voltage margin, or high-current loads at a large voltage drop.

**Negative voltages:** the 79xx family (such as 7912) gives negative outputs, used in audio circuits that need positive and negative supplies.

## The LM317 (Adjustable)

- Output adjustable from about **1.25V to 37V** using two resistors
- Up to about **1.5A** with a heat sink
- Output follows: **Vout = 1.25 x (1 + R2/R1)**, with R1 commonly 240Ω
- Needs a few volts of headroom, like the 7805

**Good for:** a variable bench supply, odd voltages such as 3.6V or 6V, and simple battery chargers.

## LDO Regulators (Low Dropout)

An LDO works like a linear regulator but needs much less headroom, often only around **1V or less**.

- **AMS1117-3.3** gives 3.3V and is common on development boards. It handles up to about 800mA.
- Useful when the input is only slightly above the output, such as a 5V supply down to 3.3V, or a single Li-ion cell (3.0V to 4.2V) feeding 3.3V.

**Good for:** 3.3V logic, sensors, ESP boards and small battery-powered designs.

## Buck Converters (Step-Down Switching)

A buck converter steps voltage **down** efficiently, often at 85% to 95%.

- **LM2596 module:** adjustable, up to about 3A, widely used
- **MP1584 module:** small, adjustable, up to about 3A
- **XL4015 module:** adjustable, higher current (up to about 5A) with a current limit option

**Good for:** powering 5V circuits from a 12V or 24V supply, high-current loads, and battery systems where efficiency matters.

**Watch out for:** switching noise. For sensitive analogue or audio circuits, follow the converter with a small LDO or add filtering.

## Boost Converters (Step-Up)

A boost converter raises voltage, for example turning a 3.7V Li-ion cell into 5V or 12V. Choose one whose current rating covers the load, and remember that the input current is higher than the output current.

## Quick Decision Guide

- **Need 5V from 9V to 12V, under 200mA:** a 7805 is fine.
- **Need 5V from 12V or more at higher current:** use a buck converter.
- **Need 3.3V from 5V:** use an LDO such as the AMS1117-3.3.
- **Need 3.3V or 5V from a Li-ion battery:** use a low-dropout regulator or a boost or buck-boost converter, depending on the voltage range.
- **Need an adjustable voltage:** use an LM317 for light loads, or an adjustable buck module for heavier ones.
- **Need negative voltage:** use a 79xx regulator or a dedicated converter.

## Common Mistakes

- **Ignoring heat.** If the regulator is too hot to touch, check the formula above.
- **Not enough input voltage.** A 7805 will not hold 5V if the input drops near 6V.
- **Missing capacitors.** Many regulators misbehave without the recommended input and output capacitors.
- **Exceeding current.** Check the real current your circuit draws, especially for motors and radios that spike.
- **Wrong pin order.** The 7805 and LM317 pin orders differ, so check the datasheet.
- **Feeding mains-powered modules incorrectly.** Use a proper isolated supply, covered in our [power supply guide](guide.html?slug=choosing-power-supply-smps-adaptor#choosing-power-supply-smps-adaptor).

---

*Aakash Electronics stocks fixed and adjustable regulators and DC-DC converter modules at SP Road, Bengaluru. [Search our parts list](/products) or bring your voltage and current numbers to the counter.*
