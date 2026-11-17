---
title: "Building a Simple Audio Amplifier: LM386, PAM8403 and TDA2030 Compared"
slug: audio-amplifier-lm386-pam8403-tda2030-compared
category: Choosing Components
target_audience: Hobbyists and students building DIY speakers, amplifiers, and audio projects
meta_description: "Compare LM386, PAM8403, and TDA2030 amplifier ICs for DIY audio: power output, supply voltage, speaker impedance, heat sinks, and which to choose for your project."
---

# Building a Simple Audio Amplifier: LM386, PAM8403 and TDA2030 Compared

A small audio amplifier is one of the most satisfying electronics builds. The choice of amplifier IC decides how loud it can get, what supply you need and how complicated the build is. This guide compares three popular options for DIY audio.

## What You Need to Decide First

1. **How loud?** Power is measured in watts. A desk speaker needs a watt or two, a room needs more.
2. **What supply do you have?** A USB 5V source, a 12V adaptor, or a dual supply?
3. **Mono or stereo?**
4. **What speaker?** Check its **impedance** (commonly 4Ω or 8Ω) and **power rating.**

## Speaker Basics

- **Impedance:** the amplifier datasheet states which impedance it suits. A lower impedance draws more current and can deliver more power, but it also stresses the amplifier more.
- **Power rating:** choose a speaker rated for at least the power the amplifier delivers, or you risk damaging it.
- Keep the speaker wire short and thick enough. Our [wires and cables guide](guide.html?slug=wires-cables-buying-guide-specifications#wires-cables-buying-guide-specifications) explains gauge.

## LM386: The Classic Small Amplifier

- A small **mono** amplifier IC in an 8-pin package
- Works from roughly **4V to 12V**
- Output is under about a watt in common circuits, so it suits **small speakers**
- Gain is adjustable from about 20 to 200 with a couple of components
- Very cheap, with few external parts

**Good for:** learning projects, small radios, intercoms and portable speakers.

**Limits:** limited power and some distortion at higher volume. It is not for room-filling sound.

## PAM8403: Compact Stereo Class-D Module

- A small **stereo class-D** amplifier that runs from **5V** (so USB power works)
- Delivers around **3W per channel** into 4Ω speakers at 5V, depending on the conditions
- **Class-D** means high efficiency, so it runs cool and needs no heat sink
- Sold as a ready-made module with a volume knob

**Good for:** USB-powered speakers, small Bluetooth speaker builds and desktop audio.

**Limits:** 5V supply limits the maximum output. Use a clean supply, because cheap USB sources add noise. Class-D modules can pick up interference, so keep wiring tidy.

## TDA2030: Bigger Sound for DIY Amplifiers

- A **mono** power amplifier IC for higher power
- Roughly **14W to 18W** into 4Ω or 8Ω speakers, depending on the supply voltage
- Works from a **single supply** (for example 12V to 24V) or a **dual supply** (such as plus and minus 12V to 18V)
- **Needs a heat sink,** since it dissipates real heat
- Needs a handful of external resistors and capacitors, and a good power supply

**Good for:** DIY hi-fi style amplifiers, larger speakers, subwoofer builds (with a filter) and workshop audio.

**Limits:** it needs a heat sink, a sturdy power supply and a layout that avoids hum. Use two ICs for stereo.

**Bigger options:** the TDA2050 and TDA7294 follow the same idea for higher power, with stricter supply and heat requirements.

## Quick Comparison

- **Smallest, cheapest, low power:** LM386
- **USB-powered stereo, runs cool:** PAM8403 module
- **Louder DIY amplifier with a heat sink:** TDA2030
- **Even louder:** TDA2050, TDA7294 or a higher-power class-D board such as the PAM8610 or TPA3116 type

## Power Supply Matters

An amplifier is only as good as its supply.
- Choose a supply that gives **more current than the amplifier draws at full volume.**
- A weak or noisy supply causes hum, distortion and low volume.
- Add **large electrolytic capacitors** near the amplifier supply pins to smooth the voltage.

See our [power supply guide](guide.html?slug=choosing-power-supply-smps-adaptor#choosing-power-supply-smps-adaptor) for sizing, and [choosing a voltage regulator](guide.html?slug=choosing-voltage-regulator-7805-lm317-buck-converter#choosing-voltage-regulator-7805-lm317-buck-converter) if you need to step voltage down.

## Common Mistakes

- **No heat sink** on a TDA-series IC. It overheats and shuts down or fails.
- **Wrong supply voltage.** Check the datasheet limits.
- **Mismatched speaker impedance or power rating.**
- **Long, thin speaker leads.**
- **Hum from poor grounding.** Keep power and signal grounds tidy and use shielded cable for the input. Our [connectors range](/products) includes RCA and audio connectors.
- **Short-circuited outputs.** A shorted speaker lead can destroy an amplifier IC.

## What to Buy for a First Build

- An amplifier IC or module that fits your supply
- A speaker with a suitable impedance and power rating
- Power supply or battery
- Capacitors and resistors (follow the datasheet circuit)
- A heat sink if required
- Input connector, volume potentiometer and wiring

---

*Aakash Electronics stocks audio amplifier ICs and boards, speakers and audio connectors at SP Road, Bengaluru. [Search our parts list](/products) or bring your speaker details to the counter.*
