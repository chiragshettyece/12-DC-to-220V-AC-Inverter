# 12V DC to 220V AC Inverter (LTspice Simulation)

LTspice simulation of a **12V DC → ~220V AC inverter** built using **IRFZ44N MOSFETs**.

> This repository contains a **simulation** (not a complete hardware build guide). Output waveform and real-world performance depend heavily on transformer choice, load, gate drive, layout, and protection circuits.

---

## What's inside

- `12V_DC_220V_AC_CONV.asc` — LTspice schematic (main simulation file)
- `irfz44n.spi` — IRFZ44N SPICE model used by the schematic
- `Output.png` — screenshot/plot of the simulated output waveform
- `README.md` — project documentation

---

## Requirements

- **LTspice** (recommended: latest LTspice from Analog Devices)

---

## How to run the simulation

1. Install **LTspice**.
2. Clone this repo:
   ```bash
   git clone https://github.com/chiragshettyece/12-DC-to-220V-AC-Inverter.git
   cd 12-DC-to-220V-AC-Inverter
Open the schematic:
Double click 12V_DC_220V_AC_CONV.asc
Make sure the MOSFET model is found:
Confirm irfz44n.spi is in the same folder as the .asc, or
Ensure the schematic includes the correct .include path to irfz44n.spi.
Click Run and view the plotted output.
Compare your output against Output.png.
Notes / Expected output
Many simple inverter topologies produce a square/modified-square wave, not a pure sine wave.
The "220V" value is typically an RMS target and depends on:
transformer turns ratio
switching frequency
duty cycle / drive signal
load and losses
Safety disclaimer (important)
High voltage is dangerous. A real 220V inverter can cause serious injury or death and can start fires.

This repo is shared for educational simulation purposes. If you build hardware:

use proper isolation and fusing
add over-current/short-circuit protection
use snubbers/clamps for inductive switching
follow safe HV measurement practices
Limitations (simulation vs real life)
Simulation may look "perfect" compared to hardware because real designs include:

transformer copper/core losses
MOSFET switching losses and heating
parasitic inductances/capacitances (layout matters a lot)
gate drive constraints (IRFZ44N needs solid gate drive for efficient switching)
License
Add a license if you want others to reuse this (MIT is common for hobby projects). If you don't add one, GitHub defaults mean reuse is legally limited.

Credits
Project by Chirag Shetty
Simulated in LTspice
Power stage uses IRFZ44N MOSFETs
