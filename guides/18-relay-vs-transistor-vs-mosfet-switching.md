---
title: "Relay vs Transistor vs MOSFET: How to Switch a Load From a Microcontroller"
slug: relay-vs-transistor-vs-mosfet-switching-loads
category: Choosing Components
target_audience: Students, hobbyists, and makers switching motors, lamps, fans, and appliances from Arduino, ESP32, or similar boards
meta_description: "How to choose between a relay, a BJT transistor, and a MOSFET for switching loads from a microcontroller: current, voltage, AC vs DC, flyback diodes, and safe wiring."
---

# Relay vs Transistor vs MOSFET: How to Switch a Load From a Microcontroller

A microcontroller pin can only give a few milliamps at 3.3V or 5V. A fan, motor, lamp or appliance needs far more. To control it you need a **switch** that the pin can operate. The three common choices are a **relay**, a **BJT transistor** and a **MOSFET**. Each suits a different job.

## The Basic Problem

A pin on an Arduino Uno can supply around 20mA safely. A 12V fan may need 300mA, and a mains lamp needs a lot more at 230V. The pin should only **control** the switch, never carry the load current itself.

## Option 1: BJT Transistor (for Small DC Loads)

A transistor such as the **BC547** (small signal) or **BC337 / 2N2222** (a bit more current) acts as an electronic switch.

- A small base current switches a larger collector current.
- Place a **resistor (about 1kΩ) between the pin and the base** to limit current.
- The load connects between the supply and the collector, and the emitter goes to ground (an NPN used as a low-side switch).

**Good for:** LEDs, small buzzers, relay coils and loads up to a few hundred milliamps at low DC voltage.

**Limits:** a BC547 handles roughly 100mA continuous, which is too little for many relay coils and motors. Check the datasheet for the current you need, and remember that a transistor is **DC only**.

## Option 2: Logic-Level MOSFET (for Larger DC Loads)

A MOSFET is controlled by **voltage** at its gate, not by current, so it wastes very little power and handles large currents.

- Choose a **logic-level** MOSFET (for example the **IRLZ44N**) if you drive it from 3.3V or 5V. Many common types such as the IRF540 need about 10V at the gate to switch fully and may overheat when driven by a 5V pin.
- Add a **resistor (about 100Ω) in series with the gate** and a **pull-down resistor (about 10kΩ) from gate to ground** so it stays off when the pin floats at start-up.
- The load connects between the supply and the drain, and the source goes to ground.

**Good for:** DC motors, LED strips, heaters, pumps and fans, and anything needing **PWM** speed or brightness control.

**Limits:** MOSFETs are **DC switches.** They cannot switch mains AC loads directly.

## Option 3: Relay (for Isolation and AC Loads)

A relay is a mechanical switch moved by a coil. It electrically **isolates** the control side from the load side.

- Relay modules usually include a driver transistor, an indicator LED and often an optocoupler.
- Ratings such as **10A / 250VAC** describe the **contacts**, not the coil.
- Many modules are **active-low:** the load turns on when the input pin goes LOW. Check your module.

**Good for:** switching mains appliances, lights and pumps, and anywhere isolation is needed.

**Limits:**
- Relays **click and wear out** over many operations, so they are not for fast switching.
- They are not suited for **PWM.**
- The coil draws noticeable current, so power the module from a suitable supply.
- Mains wiring is dangerous. Use insulated enclosures, proper terminals and a fuse, and have a qualified person check any mains work.

## Always Add a Flyback Diode for Coils and Motors

A relay coil or motor generates a voltage spike when switched off. This can destroy the transistor or MOSFET. Place a diode such as the **1N4007** across the coil or motor, with the **band toward the positive supply**. Relay modules usually include this already, but check bare relay circuits.

## Solid State Relays (SSRs)

An SSR switches AC loads with no moving parts, and it is quiet and long-lasting. It must be rated for the load, and it normally needs a heat sink at higher currents. Check that the SSR matches your load type (AC or DC).

## Quick Decision Guide

- **LED, buzzer or tiny load:** a BJT transistor
- **DC motor, fan, pump or LED strip, especially with PWM:** a logic-level MOSFET
- **Mains appliance or a load needing isolation:** a relay module, or an SSR
- **Fast switching or dimming of a DC load:** a MOSFET, never a relay
- **High-current DC load:** a MOSFET with a heat sink, or a heavy-duty relay

## Common Mistakes

- **Driving a load straight from a pin.** This can damage the controller.
- **Skipping the flyback diode.**
- **Using a non-logic-level MOSFET** on a 3.3V or 5V pin.
- **Forgetting the common ground** between the controller and the load supply. They must share a ground reference.
- **Switching mains with a MOSFET.**
- **No pull-down on the gate,** which can make loads turn on at start-up.

For motors specifically, read [motor drivers explained](guide.html?slug=motor-drivers-explained-l298n-l293d-a4988#motor-drivers-explained-l298n-l293d-a4988).

---

*Aakash Electronics stocks transistors, MOSFETs, relays and relay modules at SP Road, Bengaluru. [Search our parts list](/products) or bring your load details to the counter.*
