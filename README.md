# STM32WL Sensor Board with LoRa, ADC, and Analog Front-End

This project features a compact and versatile sensor board based on the **STM32WL55** microcontroller. The design integrates environmental sensing, motion detection, a low-noise analog front end (AFE), and long-range wireless communication via LoRa. It is intended for applications such as remote environmental monitoring, vibration tracking, and analog signal acquisition.

---

## 🔧 Features

- **STM32WL55 MCU** with integrated LoRa transceiver
- **BME280** sensor for temperature, humidity, and pressure
- **MPU-6050** 6-axis IMU for motion detection
- **External SMA input** for analog sensors (e.g., microphones, turbidity, air quality)
- **Low-noise Analog Front-End**
  - Pi filter at power input (500 kHz cutoff)
  - 3rd-order anti-aliasing filter (Butterworth topology, ~25 kHz cutoff)
  - Pseudo-differential ADC output
- **Power System**
  - SMPS (TLV62569) for digital
  - LDO (LD3985M33R) for analog
- **LoRa output stage** with matching network and filtering
- **Breakout headers** for UART, I2C, SWD

---

## 📷 Visuals

- Altium Designer 3D PCB render
- Annotated schematics for ADC/AFE, power, sensors, and RF
- Signal chain plots from LTSpice and Python

---

## 📁 Folder Structure

```
STM32WL-Sensor-Board-Report/
├── Firmware/                 # STM32CubeIDE or PlatformIO firmware
├── Hardware/                 # Altium schematics, layout, BOM
├── LTSpice_Simulations/      # AFE filter and analog chain simulations
├── Docs/                     # Project report, filter calculations
├── Images/                   # Plots, PCB renders, block diagrams
├── README.md
└── LICENSE
```

---

## 📊 Simulation & Validation

- **LTSpice**: 3rd-order LPF (RC + Sallen-Key) simulated for frequency and time-domain behavior
- **Python**: Confirmed frequency response, phase behavior, and noise attenuation using NumPy/SciPy/Matplotlib

---

## 🚀 Use Cases

- Remote environmental monitoring (weather, air, water)
- Industrial vibration tracking
- Audio / analog sensing (microphones, photodiodes)
- Smart IoT edge nodes with long-range comms

---

## 📜 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for more information.
---

## 🔋 Power Design
- LDOs for low-noise analog rails  
- Buck converters for digital supply efficiency  
- Isolated analog/digital domains with careful grounding

## 📡 RF Front-End
- Impedance-matched and filtered layout  
- Optimized for LoRa range and ETSI/FCC compliance