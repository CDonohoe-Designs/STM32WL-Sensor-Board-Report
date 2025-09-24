
# Simulation – STM32WL Sensor Node

This folder contains LTspice simulations supporting the analog front-end design of the STM32WL-based sensor platform. The simulations focus on signal integrity, anti-aliasing filter behavior, and front-end signal conditioning before digitization via the STM32 ADC.

---

##  Requirements

- **LTspice XVII** or later
- Optional: Analog Devices SPICE models (e.g., ADA4898-1, AD8138, ADA4932) from:
  - https://www.analog.com/en/design-center/design-tools-and-calculators.html

---

## Files Overview

| File | Description |
|------|-------------|
| `BodePlot_Filter.asc` | AC sweep simulation for 3rd-order anti-aliasing filter (RC + Sallen-Key) — verifies cutoff and roll-off |
| `Piezo_to_LNA.asc` | Time-domain simulation of piezo interface, matching network, and LNA (e.g., ADA4898) |
| `Piezo_to_LNA_FFT.raw` | FFT simulation output from `Piezo_to_LNA.asc` — shows frequency content of input pulse |

---

## Simulation Use Cases

### Bode Plot (AC Analysis)
- Goal: Verify anti-aliasing filter design for ~25 kHz cutoff
- Visualize gain and phase roll-off
- Confirm filter order and Q factor

### Time-Domain Analysis
- Model a Gaussian or pulsed excitation applied to piezo sensor
- Analyze signal propagation through matching network → LNA input → amplified output
- Measure ringing, overshoot, settling time

### FFT Analysis
- Run `.tran` with `Fourier` or export raw data to post-process in Python
- Confirm signal band-limiting matches expected LoRa/ADC bandwidth

---

## Sample Plots (suggested to add)

Add waveform images or Bode plots here:

- `BodePlot_Filter.png` → frequency response
- `TimeDomain_Piezo_to_LNA.png` → input vs output waveform
- `FFT_Result.png` → spectral energy before and after filtering

---

## How to Run

1. Open `.asc` file in LTspice
2. Click **Simulate → Run**
3. Use the **probe cursor** to plot:
   - AC sweep: magnitude & phase
   - Transient: input/output voltage
4. Optional: right-click → FFT for frequency analysis

---

