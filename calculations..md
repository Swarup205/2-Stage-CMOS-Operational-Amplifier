# Design Calculations

This document presents the analytical design procedure for the two-stage CMOS operational amplifier implemented using a **180 nm CMOS process**. The transistor dimensions were initially determined through analytical calculations based on the design specifications and were subsequently optimized using LTspice simulations to meet the required performance.

---

# Design Specifications

| Parameter | Value |
|-----------|-------|
| Technology | 180 nm CMOS |
| Supply Voltage (VDD) | 1.8 V |
| DC Gain | ≥ 60 dB |
| Gain-Bandwidth Product (GBW) | 30 MHz |
| Phase Margin | ≥ 60° |
| Slew Rate | 40 V/µs |
| Load Capacitance (CL) | 2 pF |
| Power Dissipation | ≤ 300 µW |
| Input Common-Mode Range (ICMR) | 0.8–1.6 V |

---

# Technology Parameters

| Parameter | Value |
|-----------|-------|
| NMOS Threshold Voltage (VTH,n) | 0.37 V |
| PMOS Threshold Voltage (VTH,p) | -0.39 V |
| Electron Mobility (μn) | 274 cm²/V·s |
| Hole Mobility (μp) | 116 cm²/V·s |
| Gate Oxide Thickness (tox) | 4.1 nm |
| Gate Oxide Capacitance (Cox) | 8.42 mF/m² |

---

# Compensation Capacitor

The Miller compensation capacitor was selected to obtain a phase margin greater than **60°**.

Cc > 0.22 × CL

Cc > 0.22 × 2 pF

Cc > 440 fF

Final selected value:

**Cc = 500 fF**

---

# Bias Current

The required tail current was determined from the slew-rate specification.

**SR = I5 / Cc**

Given:

- Slew Rate = 40 V/µs
- Cc = 500 fF

Therefore,

**I5 = SR × Cc**

**I5 = 20 µA**

---

# Input Stage Transconductance

The input differential pair transconductance was estimated using

**gm1 = 2π × GBW × Cc**

The final value was verified and optimized through simulation.

---

# Second Stage Design

To obtain a phase margin greater than **60°**, the second-stage transconductance was selected as

**gm6 ≈ 10 × gm1**

The final transistor sizing was refined through iterative simulation.

---

# Current Mirror Design

The current mirrors were designed according to the required current ratios using

**(W/L)₁ / (W/L)₂ = ID₁ / ID₂**

The final transistor dimensions were obtained after iterative optimization.

---

# Final Transistor Dimensions

| Transistor | W/L |
|------------|----:|
| M1 | 5 |
| M2 | 5 |
| M3 | 7 |
| M4 | 7 |
| M5 | 3 |
| M6 | 63 |
| M7 | 13.5 |
| M8 | 3 |

---

# Saturation Verification

The operating-point analysis confirms the operating region of each MOSFET across the specified input common-mode range.

### NMOS Saturation Condition

**VDS > VGS − VTH**

### PMOS Saturation Condition

**VSD > VSG − |VTH|**

---

## ICMR = 0.8 V

| MOSFET | VDS/VSD (V) | VGS − VTH / VSG − |VTH| (V) | Region |
|---------|------------:|-------------------------:|--------|
| M1 | 0.915 | 0.186 | Saturation |
| M2 | 0.915 | 0.186 | Saturation |
| M3 | 0.641 | 0.166 | Saturation |
| M4 | 0.641 | 0.166 | Saturation |
| M5 | 0.244 | 0.275 | Near Saturation |
| M6 | 1.192 | 0.251 | Saturation |
| M7 | 0.608 | 0.275 | Saturation |

---

## ICMR = 1.6 V

| MOSFET | VDS/VSD (V) | VGS − VTH / VSG − |VTH| (V) | Region |
|---------|------------:|-------------------------:|--------|
| M1 | 0.125 | 0.205 | Near Saturation |
| M2 | 0.125 | 0.205 | Near Saturation |
| M3 | 0.650 | 0.260 | Saturation |
| M4 | 0.650 | 0.260 | Saturation |
| M5 | 1.025 | 0.276 | Saturation |
| M6 | 0.677 | 0.260 | Saturation |
| M7 | 1.123 | 0.276 | Saturation |

---

# Final Small-Signal Parameters

## ICMR = 0.8 V

| MOSFET | gm (µS) | gds (µS) |
|---------|--------:|---------:|
| M1 | 70.25 | 0.950 |
| M2 | 70.25 | 0.950 |
| M3 | 114.31 | 1.130 |
| M4 | 114.31 | 1.130 |
| M5 | 137.96 | 1.897 |
| M6 | 1071.81 | 10.670 |
| M7 | 291.67 | 8.900 |

---

## ICMR = 1.6 V

| MOSFET | gm (µS) | gds (µS) |
|---------|--------:|---------:|
| M1 | 99.80 | 1.023 |
| M2 | 99.80 | 1.023 |
| M3 | 78.69 | 1.128 |
| M4 | 78.69 | 1.128 |
| M5 | 148.19 | 2.045 |
| M6 | 707.88 | 11.000 |
| M7 | 241.24 | 9.167 |

---

# Voltage Gain

The overall open-loop voltage gain is

**Av = gm₁(ro₂ || ro₄) × gm₆(ro₆ || ro₇)**

---

## ICMR = 0.8 V

| Stage | Gain |
|-------|------:|
| First Stage | 30.58 dB |
| Second Stage | 34.77 dB |
| **Overall Gain** | **65.35 dB** |

---

## ICMR = 1.6 V

| Stage | Gain |
|-------|------:|
| First Stage | 32.94 dB |
| Second Stage | 30.91 dB |
| **Overall Gain** | **63.84 dB** |

The simulated open-loop gain exceeds the target specification of **60 dB** over the entire input common-mode range.

---

# Power Dissipation

Using

- ID5 = 20 µA
- ID6 = 90 µA
- VDD = 1.8 V

The total power dissipation is calculated as

**P = VDD × (ID5 + ID6)**

Substituting the values,

**P = 1.8 × (20 + 90) µA**

**P = 198 µW**

Since

**198 µW < 300 µW**

the designed operational amplifier satisfies the required power dissipation specification.
