# Performance Summary

The two-stage CMOS operational amplifier was designed and optimized using a 180 nm CMOS process. Analytical calculations were used for the initial design, followed by LTspice simulations to optimize the transistor dimensions and verify the required performance specifications.

## Final Performance

| Parameter | Specification | Achieved |
|-----------|--------------:|---------:|
| Technology | 180 nm CMOS | 180 nm CMOS |
| Supply Voltage (VDD) | 1.8 V | 1.8 V |
| DC Gain | ≥ 60 dB | 65.35 dB (ICMR = 0.8 V)<br>63.84 dB (ICMR = 1.6 V) |
| Gain-Bandwidth Product (GBW) | 30 MHz | ~30 MHz |
| Phase Margin | ≥ 60° | >60° |
| Slew Rate | 40 V/µs | 40 V/µs |
| Input Common-Mode Range (ICMR) | 0.8–1.6 V | 0.8–1.6 V |
| Load Capacitance | 2 pF | 2 pF |
| Compensation Capacitor | 500 fF | 500 fF |
| Power Dissipation | ≤ 300 µW | 198 µW |

---

## Key Highlights

- Designed using a **180 nm CMOS process** with a **1.8 V** supply.
- Achieved an open-loop DC gain exceeding **60 dB** over the specified input common-mode range.
- Realized a **30 MHz gain-bandwidth product (GBW)**.
- Maintained a **phase margin greater than 60°**, ensuring stable closed-loop operation.
- Achieved the target **slew rate of 40 V/µs** using Miller compensation.
- Verified operation across an **ICMR of 0.8 V to 1.6 V**.
- Total power dissipation is **198 µW**, satisfying the low-power design requirement.
- Device operating points and small-signal parameters were verified through LTspice operating-point analysis.

---

## Conclusion

The designed two-stage CMOS operational amplifier successfully meets the targeted specifications for gain, bandwidth, stability, slew rate, input common-mode range, and power consumption. The analytical design methodology, followed by simulation-based optimization, demonstrates a practical analog CMOS amplifier suitable for educational purposes and analog integrated circuit design applications.
