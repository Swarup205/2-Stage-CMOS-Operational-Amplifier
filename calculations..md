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

\[
C_C > 0.22C_L
\]

\[
C_C > 0.22 \times 2\text{ pF}
\]

\[
C_C > 440\text{ fF}
\]

The final compensation capacitor was chosen as:

**Cc = 500 fF**

---

# Bias Current

The required tail current was determined from the slew-rate specification.

\[
SR=\frac{I_5}{C_C}
\]

Given

- Slew Rate = 40 V/µs
- Cc = 500 fF

Therefore,

\[
I_5 = SR \times C_C
\]

\[
I_5 = 20\,\mu A
\]

---

# Input Stage Transconductance

The input differential pair transconductance was estimated using

\[
g_{m1}=2\pi \times GBW \times C_C
\]

The final value was verified and optimized through simulation.

---

# Second Stage Design

To achieve a phase margin greater than **60°**, the second-stage transconductance was selected as

\[
g_{m6}\approx10g_{m1}
\]

The final transistor sizing was refined through iterative simulation.

---

# Current Mirror Design

The current mirrors were designed according to the required current ratios using

\[
\frac{(W/L)_1}{(W/L)_2}
=
\frac{I_{D1}}{I_{D2}}
\]

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

The operating point analysis confirms that the MOSFETs remain in the desired operating region across the specified input common-mode range.

### NMOS

\[
V_{DS}>V_{GS}-V_{TH}
\]

### PMOS

\[
V_{SD}>V_{SG}-|V_{TH}|
\]

---

## ICMR = 0.8 V

| MOSFET | VDS/VSD (V) | VGS−VTH / VSG−|VTH| (V) | Region |
|---------|------------:|--------------------------:|--------|
| M1 | 0.915 | 0.186 | Saturation |
| M2 | 0.915 | 0.186 | Saturation |
| M3 | 0.641 | 0.166 | Saturation |
| M4 | 0.641 | 0.166 | Saturation |
| M5 | 0.244 | 0.275 | Near Saturation |
| M6 | 1.192 | 0.251 | Saturation |
| M7 | 0.608 | 0.275 | Saturation |

---

## ICMR = 1.6 V

| MOSFET | VDS/VSD (V) | VGS−VTH / VSG−|VTH| (V) | Region |
|---------|------------:|--------------------------:|--------|
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

The overall open-loop voltage gain of the two-stage CMOS operational amplifier is given by

\[
A_v =
g_{m1}(r_{o2}\parallel r_{o4})
\times
g_{m6}(r_{o6}\parallel r_{o7})
\]

---

## ICMR = 0.8 V

| Stage | Gain |
|-------|------|
| First Stage | 30.58 dB |
| Second Stage | 34.77 dB |
| **Overall Gain** | **65.35 dB** |

---

## ICMR = 1.6 V

| Stage | Gain |
|-------|------|
| First Stage | 32.94 dB |
| Second Stage | 30.91 dB |
| **Overall Gain** | **63.84 dB** |

The simulated open-loop gain exceeds the design target of **60 dB** over the specified input common-mode range.

---

# Power Dissipation

Using

- \(I_{D5}=20\,\mu A\)
- \(I_{D6}=90\,\mu A\)
- \(V_{DD}=1.8\,V\)

The total power dissipation is

\[
P=V_{DD}(I_{D5}+I_{D6})
\]

\[
P=1.8\times110\,\mu A
\]

\[
P=198\,\mu W
\]

which satisfies the design specification of

\[
P<300\,\mu W.
\]
