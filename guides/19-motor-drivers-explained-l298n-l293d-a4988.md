---
title: "Motor Drivers Explained: L298N, L293D, TB6612 and A4988 Compared"
slug: motor-drivers-explained-l298n-l293d-a4988
category: Choosing Components
target_audience: Robotics students, hobbyists, and prototype builders choosing a driver for DC, stepper, or servo motors
meta_description: "How to choose a motor driver: L298N vs L293D vs TB6612FNG for DC motors, A4988 and DRV8825 for steppers, why servos and BLDC motors differ, and how to avoid common wiring mistakes."
---

# Motor Drivers Explained: L298N, L293D, TB6612 and A4988 Compared

A microcontroller cannot power a motor directly. Motors need far more current than a pin can supply, and they push voltage spikes back into the circuit. A **motor driver** sits between the controller and the motor to handle that. The right driver depends on the **type of motor** and how much current it draws.

If you are switching a simple on/off load rather than controlling direction or speed, see [relay vs transistor vs MOSFET](guide.html?slug=relay-vs-transistor-vs-mosfet-switching-loads#relay-vs-transistor-vs-mosfet-switching-loads).

## First, Know Your Motor Type

- **Brushed DC motor** (the common yellow geared motor): two wires. Direction is set by polarity and speed by PWM. Needs an **H-bridge driver.**
- **Stepper motor:** moves in precise steps. Needs a **stepper driver.**
- **Servo motor:** has a built-in controller. It needs only a control signal and a suitable power supply, **no driver.**
- **Brushless (BLDC) motor:** used in drones and fans. Needs an **ESC** (electronic speed controller).

## What an H-Bridge Does

An H-bridge lets you run a DC motor **forward, backward, or stop**, and with PWM control its speed. Most DC motor driver boards contain one or two H-bridges, so they can drive one or two motors.

## DC Motor Drivers Compared

**L298N**
- Dual H-bridge, about **2A per channel** (check the real motor current)
- Supply range roughly **5V to 35V**
- Based on older bipolar technology, so it loses about **2V** across the driver and gets **hot**
- Cheap, common, and very popular on robot kits

**L293D**
- Dual H-bridge, about **600mA per channel** (1.2A peak)
- Supply range roughly **4.5V to 36V**
- Includes built-in protection diodes
- Suits small hobby motors and toys

**TB6612FNG**
- Dual H-bridge with **MOSFET** outputs, around **1.2A continuous** per channel (higher peak)
- Much **more efficient** and cooler than the L298N, with a smaller voltage drop
- A good upgrade for battery-powered robots

**Quick comparison**
- **Small motors, low cost:** L293D
- **Common beginner robot with medium motors:** L298N (accept the heat and voltage drop)
- **Battery robot where efficiency matters:** TB6612FNG
- **Large motors (several amps):** use a higher-rated MOSFET driver module or a dedicated high-current driver

## Stepper Motor Drivers

**A4988**
- Drives bipolar steppers up to about **2A per coil** with proper cooling
- Microstepping up to **1/16**
- Takes simple **STEP** and **DIR** inputs
- Used widely in 3D printers and CNC projects

**DRV8825**
- Similar to the A4988, with up to **1/32 microstepping** and slightly higher current

**Setting the current limit:** these drivers have a small trim potentiometer. The current limit follows **I = Vref / (8 x Rsense)**, where Rsense is the value of the sense resistor on your board. Check that value for your specific module, then set Vref with a multimeter. Too high a setting overheats the motor and driver, and too low causes missed steps.

**Important:** add a **100µF capacitor** across the motor supply pins close to the driver, and **never connect or disconnect the motor while powered.** This can destroy the driver.

## Servos

Hobby servos (SG90, MG90S, MG995) need a **5V supply** and a **PWM control wire.** Power them from a separate supply or regulator when using several, because they draw a lot of current when moving. Share the ground with the controller.

## Brushless Motors and ESCs

A BLDC motor needs an **ESC** rated for the motor's current (for example a 30A ESC). The ESC takes a servo-style control signal. Match the ESC rating to the motor and battery.

## Powering the Motors Correctly

- **Use a separate supply for the motors** where possible, with a **common ground** shared with the controller.
- Motors draw high **stall current** when blocked. Pick a driver and supply that can handle it for a moment.
- Voltage drops from motors can **reset the controller.** A separate supply or a strong regulator avoids this. See [choosing a voltage regulator](guide.html?slug=choosing-voltage-regulator-7805-lm317-buck-converter#choosing-voltage-regulator-7805-lm317-buck-converter).

## Common Mistakes

- **Choosing a driver by the voltage rating alone.** Check the current.
- **Forgetting that the L298N drops about 2V,** so a 6V motor on a 6V supply runs slower than expected.
- **No heat sink** on a hot driver.
- **Powering motors from the Arduino 5V pin.**
- **Hot-plugging steppers.**
- **Not sharing ground.**

For a complete robot plan, read our [guide to building a rover](guide.html?slug=building-rover-robotics-prototype-component-sourcing#building-rover-robotics-prototype-component-sourcing).

---

*Aakash Electronics stocks motor driver ICs and modules, geared motors, steppers and servos at SP Road, Bengaluru. [Search our parts list](/products) or bring your motor details to the counter.*
