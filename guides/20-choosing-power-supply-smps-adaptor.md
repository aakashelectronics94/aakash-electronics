---
title: "How to Choose a Power Supply or SMPS Adaptor for Your Project"
slug: choosing-power-supply-smps-adaptor
category: Choosing Components
target_audience: Students, hobbyists, CCTV installers, and makers choosing an adaptor or SMPS for electronics projects
meta_description: "How to choose a power supply or SMPS adaptor: voltage, current rating, polarity, plug size, regulated vs unregulated, safety marks, and sizing for Arduino, LED strips, and CCTV."
---

# How to Choose a Power Supply or SMPS Adaptor for Your Project

A wrong power supply is one of the most common reasons electronics fail, behave strangely or get damaged. The good news is that picking the right one only needs four checks: **voltage, current, polarity and plug size**, plus a look at quality.

## The Four Checks

**1. Voltage: match it to the device**
The output voltage must match what your device needs. A 12V device on a 9V supply may not work, and on a 24V supply it may be destroyed. If a device accepts a range, the label usually says so (for example "7-12V").

**2. Current: the supply must be able to give enough**
The supply's current rating (in amps or milliamps) must be **at least as high as the device draws.** A device only takes what it needs, so a higher-rated supply is safe, but a lower-rated one will overheat or sag.

**Rule of thumb:** choose a supply with **20% to 50% more current capacity** than your load's maximum. Running a supply at its limit shortens its life.

**3. Polarity: positive and negative must match**
Barrel plugs are usually **centre-positive,** but not always. The device label shows a small symbol with the polarity. Reversed polarity can damage electronics instantly.

**4. Plug size: the connector must fit**
The most common barrel sizes are **5.5mm x 2.1mm** and **5.5mm x 2.5mm.** Using a plug that nearly fits can cause poor contact and heating. Our [connectors and sockets](/products) listing covers these sizes.

## How to Calculate What You Need

**Power (watts) = Voltage x Current**

Example: a 12V LED strip that draws 3A needs 36W. A 12V 5A supply (60W) gives comfortable headroom.

If you add several loads on one supply, add their currents together at the same voltage.

## SMPS vs Linear Adaptors

- **SMPS (switched-mode):** small, light, efficient and common today. Quality varies a lot, and cheap ones can be noisy.
- **Linear (transformer-based):** heavier and less efficient, but quiet. Older adaptors are often of this type.

## Regulated vs Unregulated

- **Regulated:** holds a steady output voltage even when the load changes. Choose this for electronics.
- **Unregulated:** the voltage can be much higher than the label when lightly loaded. It can damage sensitive circuits. Avoid it for microcontrollers and modules unless you add regulation.

## Common Uses and What to Pick

**Arduino and microcontroller boards**
- Arduino Uno or Nano: a regulated **7V to 12V** adaptor into the barrel jack or Vin, or a 5V supply to the USB or 5V pin.
- ESP32 and ESP8266 boards: usually **5V** through USB or the 5V pin, as they run a 3.3V regulator on board.

**LED strips**
- Check whether the strip is **5V, 12V or 24V.** Match the supply voltage exactly, and size the current from the strip's watts per metre multiplied by the length.

**CCTV cameras**
- Most analogue and many IP cameras use **12V DC.** A single camera usually needs about 1A to 2A, and a multi-camera power box needs the total of all cameras plus margin.

**Laptops**
- Laptop adaptors are **model-specific** (voltage commonly 19V or 19.5V). Match the voltage, the current (equal or higher), and the plug size.

**Chargers**
- Phone and power-bank chargers output 5V and may support fast-charging protocols. A normal 5V project only needs a stable 5V supply.

## Safety and Quality

- Look for a proper **BIS/ISI marking** and a clearly printed rating on adaptors.
- Be cautious of **very light adaptors** that claim high wattage, since the label may not be honest.
- Test the output with a multimeter before connecting a valuable device.
- Keep supplies **cool and ventilated,** and do not cover them while in use.
- Replace any adaptor with **damaged insulation, a hot casing or a burning smell.**
- Never open a mains adaptor. It can hold dangerous voltage even after unplugging.

## Powering Circuits That Need a Different Voltage

If your supply voltage is higher than the circuit needs, step it down with a regulator or buck converter, as covered in [choosing a voltage regulator](guide.html?slug=choosing-voltage-regulator-7805-lm317-buck-converter#choosing-voltage-regulator-7805-lm317-buck-converter).

## Quick Checklist

1. Voltage matches the device
2. Current is higher than the load, with 20% to 50% margin
3. Polarity symbol matches
4. Plug size fits firmly
5. Regulated output
6. Proper safety marking and a believable weight

---

*Aakash Electronics stocks SMPS adaptors, CCTV power supplies, laptop adaptors, converters and chargers at SP Road, Bengaluru. [Search our parts list](/products) or bring the device label to the counter.*
