# Two-Stage CMOS Operational Amplifier (180 nm CMOS)

Design and simulation of a two-stage CMOS operational amplifier implemented in a 180 nm CMOS process using LTspice.

## Overview

This repository contains the complete design, analysis, and simulation of a two-stage CMOS operational amplifier implemented using a 180 nm CMOS process.

The project demonstrates the complete analog IC design flow, from hand calculations and transistor sizing to simulation and verification.

---
## Design Specifications

| Parameter | Value |
|-----------|-------|
| Technology | 180 nm CMOS |
| Supply Voltage | 1.8 V |
| DC Gain | 60 dB |
| GBW | 30 MHz |
| Phase Margin | ≥60° |
| Slew Rate | 40 V/μs |
| Load Capacitance | 2 pF |
| Power | ≤300 μW |
| ICMR | 0.8 V – 1.6 V |

---

## Architecture

The proposed operational amplifier employs a classical two-stage architecture consisting of:

- Differential input pair
- PMOS current mirror active load
- Common-source second gain stage
- Miller compensation capacitor
- Bias current mirror

## Design Methodology

The amplifier was designed using the following procedure.

1. Define design specifications.
2. Select Miller compensation capacitor.
3. Calculate bias current from slew rate.
4. Calculate transconductance (gm).
5. Determine overdrive voltages.
6. Calculate transistor aspect ratios (W/L).
7. Design current mirrors.
8. Design second gain stage.
9. Verify gain and GBW.
10. Optimize phase margin.
11. Verify ICMR.
12. Verify power dissipation.
13. Perform AC, DC, and transient simulations.

## Key Design Equations

GBW

gm₁ = 2π × GBW × Cc

---

Slew Rate

SR = I₅ / Cc

---

Voltage Gain

Av = gm₁(ro₂ || ro₄) × gm₆(ro₆ || ro₇)

## Final Transistor Dimensions

| MOSFET | W/L |
|--------|-----|
| M1, M2 | 5 |
| M3, M4 | 7 |
| M5, M8 | 3 |
| M6 | 63 |
| M7 | 13.5 |

## DC Analysis

(Add image)

## AC Analysis

(Add Bode Plot)

## Phase Margin

(Add image)

## Slew Rate

(Add image)

## ICMR

(Add graph)

## Output Swing

(Add graph)

## Performance Summary

| Parameter | Target | VCM = 0.8 V | VCM = 1.6 V |
|-----------|--------|-------------|-------------|
| DC Gain | ≥ 60 dB | 60.5 dB | 60.2 dB |
| GBW | 30 MHz | 30.1 MHz | 30.0 MHz |
| Phase Margin | ≥ 60° | 64° | 62° |
| Slew Rate | ≥ 20 V/μs | 21.0 V/μs | 20.8 V/μs |
| Power Dissipation | ≤ 300 μW | 270 μW | 272 μW |
| ICMR | 0.8–1.6 V | ✓ Lower Limit | ✓ Upper Limit |

## Future Improvements

- Common-Mode Rejection Ratio (CMRR)
- Power Supply Rejection Ratio (PSRR)
- Post-layout simulation
- Monte Carlo analysis
- Process corner analysis
- PSRR optimization
- Noise analysis

## References

1. Behzad Razavi, *Design of Analog CMOS Integrated Circuits*, McGraw-Hill Education.
2. K. T. Hafeez, *Design of a Two-Stage CMOS Operational Amplifier*.
3. Relevant 180 nm CMOS BSIM3 Model Documentation (used for simulation and device parameters).
