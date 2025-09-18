---
title: "[]{#_heading=h.gd7cryi9nvie .anchor}**Introduction : Versatile
  Sensor Board Design with STM32WL, Analog Front-End, LoRa Wireless, and
  External SMA Sensor Connector**"
---

**By: Caoilte Donohoe**

# STM32WL Sensor Node with Analog Front-End and LoRa

This project implements a compact, low-power wireless sensing node based
on the STM32WL microcontroller. It is designed for field-deployable
sensing applications requiring reliable analog signal capture,
anti-aliasing, and long-range LoRa wireless transmission. The system
combines analog and RF circuit design, simulation-backed validation, and
practical embedded design practices.

![](media/image1.jpg){width="6.0in" height="4.236111111111111in"}

## Key Features

-   \- External Analog Sensor Interface: SMA and breakout headers
    support pseudo-differential analog inputs. The analog front-end
    includes filtering, biasing, and ESD protection for robust signal
    acquisition.

-   \- 3rd-Order Anti-Aliasing Filter: A Sallen-Key Butterworth topology
    is used to ensure flat passband and 20 kHz bandwidth, with
    simulation-verified roll-off and minimal phase distortion.

-   \- RF Output Network: Based on STM32 AN5457 guidance, the RFO_LP
    output is impedance-matched to 50 Ω using a discrete L-match network
    followed by notch and π-filters to suppress 2nd and 3rd harmonics.
    The full RF path is simulated in LTspice to optimize S21, group
    delay, and out-of-band rejection.

-   \- Pseudo-Differential ADC Drive: The analog input drives one side
    of the ADC, while the other is tied to a low-impedance reference,
    enabling common-mode noise rejection without needing a fully
    differential driver.

-   \- Clean Power Architecture: An SMPS supplies the digital domain,
    while a low-noise LDO powers the analog and RF sections to maintain
    high signal integrity.

-   \- Breakout Connectivity: UART (TX/RX), I²C, SPI for LoRa, SWD
    debug, and dedicated analog headers are provided for system debug
    and expansion.

## Tools Used

-   \- LTspice: RF path and anti-aliasing filter simulation, S-parameter
    approximation, group delay evaluation

-   \- Altium Designer: Professional schematic and PCB layout of 4-layer
    board with controlled impedance routing

-   \- Python (Jupyter): Post-processing of waveform simulation results
    and FFT harmonic analysis

## Applications

Ideal for deployment in IoT sensor networks, remote analog monitoring,
field environmental data logging, or vibration-sensing telemetry
platforms where accurate analog front-end performance is critical.
