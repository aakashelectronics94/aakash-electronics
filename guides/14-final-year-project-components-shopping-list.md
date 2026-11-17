---
title: "Final-Year Engineering Project Components: A Shopping List by Project Type"
slug: final-year-engineering-project-components-shopping-list
category: Students & Labs
target_audience: Final-year engineering and diploma students planning IoT, robotics, automation, and power electronics projects
meta_description: "A practical component shopping list for final-year engineering projects in Bengaluru: IoT, robotics, home automation, smart agriculture, and solar/power projects, with tips on avoiding common buying mistakes."
---

# Final-Year Engineering Project Components: A Shopping List by Project Type

Every year, final-year students lose days because they bought the wrong module, forgot a power supply, or discovered a part was incompatible after the deadline was close. This guide gives starting shopping lists for the most common project types, plus a checklist that prevents the usual mistakes.

Treat these lists as a starting point. Your guide or faculty advisor may require specific parts, so confirm that first.

## Before You Buy Anything

1. **Finalise the block diagram first.** Know your sensors, controller, power source and output before you shop.
2. **Write the power budget.** Add up the current each part needs and choose a supply that covers it with margin.
3. **Check logic levels.** Many modules are 3.3V and some boards are 5V. Mixing them without level shifting can damage parts.
4. **Buy spares of cheap parts.** LEDs, resistors, jumper wires and transistors are cheap and easy to damage.
5. **Buy everything in one go.** Mixed deliveries cause delays, and one missing item stops the whole build.

## Project Type 1: IoT and Home Automation

**Typical parts**
- ESP32 or ESP8266 board (Wi-Fi), or Arduino with a Wi-Fi module
- Relay module (1, 2 or 4 channel) for switching appliances
- Temperature and humidity sensor (DHT11 or DHT22)
- PIR motion sensor
- Light sensor (LDR) or a light sensor module
- Jumper wires, breadboard, 5V power supply
- Optional: OLED display, buzzer

**Watch out for:** mains wiring is dangerous. Use an enclosure, insulated terminals and a proper fuse, and have your faculty or a qualified person check the mains side.

## Project Type 2: Smart Agriculture

**Typical parts**
- ESP32 or Arduino
- Soil moisture sensor
- Temperature and humidity sensor
- Water pump (small DC) with a relay or MOSFET driver
- Rain sensor, optional
- Power supply or battery with a suitable regulator
- Optional: GSM module for alerts

**Watch out for:** soil moisture probes corrode over time, so use corrosion-resistant ones and power them only when reading.

## Project Type 3: Robotics (Line Follower, Obstacle Avoider, Rover)

**Typical parts**
- Arduino Uno or Nano
- Motor driver (L298N, L293D or TB6612)
- DC geared motors and wheels with a chassis
- Ultrasonic sensor (HC-SR04) or IR sensors
- Battery pack, plus a regulator or a buck converter
- Optional: Bluetooth module (HC-05) for phone control

See our [guide to building a rover or robotics prototype](guide.html?slug=building-rover-robotics-prototype-component-sourcing#building-rover-robotics-prototype-component-sourcing) for a stage-by-stage plan, and [motor drivers explained](guide.html?slug=motor-drivers-explained-l298n-l293d-a4988#motor-drivers-explained-l298n-l293d-a4988) for choosing the right driver.

**Watch out for:** motors cause voltage drops that reset the controller. Give the motors a separate supply or a strong regulator.

## Project Type 4: Power Electronics and Solar

**Typical parts**
- Solar panel (small, matched to your charge circuit)
- Charge controller module or a TP4056 for single Li-ion cells, with protection
- Li-ion or lead-acid battery with a holder or connector
- Buck or boost converter module
- Current and voltage sensor (INA219 or ACS712)
- Fuses, diodes, heat sinks

**Watch out for:** lithium cells need proper protection circuits. Never charge them without a protection or BMS module, and never short them.

## Project Type 5: Embedded and Display Projects

**Typical parts**
- Microcontroller board (Arduino, STM32 or ESP32)
- LCD 16x2, OLED or TFT display
- Keypad or push buttons
- RTC module (DS3231) for timekeeping
- Buzzer and LEDs
- Memory card module, optional

## Common Parts Almost Every Project Needs

- Breadboard and jumper wires (male-male, male-female, female-female)
- Assorted resistors and a few capacitors (100nF and 100µF are very common)
- LEDs in a few colours
- Push buttons and a slide switch
- A multimeter, soldering iron, solder and flux
- A regulated power supply or battery pack

For more on the basics, read [passive vs active components](guide.html?slug=passive-vs-active-components-guide#passive-vs-active-components-guide) and our guide to [choosing sensor modules](guide.html?slug=choosing-sensor-modules-robotics-iot#choosing-sensor-modules-robotics-iot).

## Mistakes That Cost Students Time

- **Buying before designing.** Parts bought "just in case" often go unused.
- **Ignoring power.** Many "my project doesn't work" cases are really power problems.
- **No spare parts.** One burnt sensor should not delay your demo.
- **Last-minute shopping.** Allow at least a week of buffer before your review.
- **Not testing modules individually.** Test each module alone before integrating.

## Getting Help With Your List

Bring your block diagram or a written list to the counter, and we can help you check that the parts fit together before you pay. You can also search our parts list online first.

---

*Aakash Electronics has supplied students, colleges and hobbyists from SP Road, Bengaluru since 1994. [Search our parts list](/products) or visit the counter with your project list.*
