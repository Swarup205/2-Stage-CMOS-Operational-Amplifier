# Design Calculations

This document presents the complete analytical design procedure of the two-stage CMOS operational amplifier implemented in a 180 nm CMOS process.

The transistor dimensions were calculated analytically based on the given specifications before simulation and iterative optimization.

## Design Specifications

| Parameter | Value |
|-----------|-------|
| Technology | 180 nm CMOS |
| VDD | 1.8 V |
| Gain | 60 dB |
| GBW | 30 MHz |
| Phase Margin | ≥60° |
| Slew Rate | 20 V/µs |
| CL | 2 pF |
| Power | ≤300 µW |
| ICMR | 0.8–1.6 V |

## Technology Parameters

| Parameter | Value |
|-----------|-------|
| Vth,n | 0.37 V |
| Vth,p | -0.39 V |
| μn | 274 cm²/V·s |
| μp | 116 cm²/V·s |
| tox | 4.1 nm |
| Cox | 8.42 mF/m² |

## Step 1 – Compensation Capacitor

The Miller compensation capacitor was selected to obtain a phase margin greater than 60°.

Chosen value:

Cc > 0.22 * CL
Cc > 440fF
Cc = 500fF

## Step 2 – Bias Current

Required Slew Rate

SR = 40 V/µs

Using

SR = I5/Cc

I5 = SR × Cc

Therefore,

I5 = 20 A

## Step 3 – Input Stage Transconductance

Using

gm1 = 2π × GBW × Cc

Therefore,

gm1 = 160 S

## Step 4 – Second Stage

For a phase margin greater than 60°

gm6 ≈ 10 gm1

Therefore,

gm6 = 1600 S

## Step 5 – Voltage Gain

Av = gm1(ro2 || ro4) × gm6(ro6 || ro7)

Required

Av = 1000 V/V

The required output resistances were calculated accordingly.

## Step 6 – Current Mirror Design

Current mirrors were designed using

(W/L)1/(W/L)2 = ID1/ID2

The transistor dimensions were selected according to the required current ratios.

## Final Transistor Dimensions

| Transistor | W/L |
|-------------|-----|
| M1 | |
| M2 | |
| M3 | |
| M4 | |
| M5 | |
| M6 | |
| M7 | |

## Saturation Verification

All MOSFETs satisfy the saturation condition.

NMOS:

VDS > VGS − VTH

PMOS:

VSD > VSG − |VTH|

Verified for

- M1
- M2
- M3
- M4
- M5
- M6
- M7

## Final Small-Signal Parameters

| MOSFET | gm | gds |
|---------|----|-----|
| M1 | | |
| M2 | | |
| M3 | | |
| M4 | | |
| M5 | | |
| M6 | | |
| M7 | | |

## Power Dissipation 
ID5 = 20µA
ID6 = 90µA
VDD = 1.8V

Power Dissippation = 1.8 * (ID5 + ID6) = 198µW (<300µW)
