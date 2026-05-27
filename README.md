# BLE Receiver Front End Design

A mixed-signal RF project focused on the design and implementation of a low-power Bluetooth Low Energy (BLE) receiver front end, including Low Noise Amplifier (LNA), mixer, PCB layout, impedance matching, and RF performance optimization.

---

## Project Overview

This project presents the design of a low-power Bluetooth Low Energy (BLE) receiver front end operating near 2.45 GHz. The receiver chain includes:

- Low Noise Amplifier (LNA)
- Passive Mixer
- LC Matching Networks
- PCB RF Layout Design
- Frequency Conversion Analysis

The project focuses on achieving:
- Low power consumption
- Improved RF gain
- Proper impedance matching
- Compact PCB implementation

---

## Design Objectives

- Design a BLE receiver operating at 2.45 GHz
- Improve gain performance of the LNA
- Implement low-power passive mixer architecture
- Design RF PCB traces for controlled impedance
- Minimize power consumption while maintaining signal integrity

---

## Receiver Architecture

### Main Components

- Single-transistor Low Noise Amplifier (LNA)
- Passive diode mixer
- LC matching network
- RF filters
- Intermediate Frequency (IF) output stage

---

## Initial Design Challenges

### Observed Problems

- Expected gain: 10–15 dB
- Actual gain: ~0 dB

### Root Causes

- High input resistance prevented transistor activation
- Poor impedance matching
- RC load reduced RF gain
- Insufficient reactive loading

---

## Circuit Improvements

### Modifications Applied

- Reduced input resistance (R1)
- Replaced resistive load with inductive load
- Added emitter bypass capacitor (CE)
- Increased input/output inductance
- Improved matching capacitors

### Results

| Parameter | Before Fix | After Fix |
|-----------|------------|------------|
| Gain | ~0 dB | 12 dB |
| RF Performance | Poor | Improved |
| Power Efficiency | Moderate | High |

---

## Mixer Design

The receiver uses a passive diode mixer for low-power operation.

### Mixer Characteristics

- Minimal DC power consumption
- Simple architecture
- RF and LO frequency mixing
- Frequency downconversion capability

### Frequency Mixing Example

\[
f_{RF} + f_{LO} \approx 4.89 \text{ GHz}
\]

Fourier simulations confirmed output peaks near:
- 4.89 GHz
- 4.90 GHz

---

## Gain Equation

### Voltage Gain

\[
Gain = \frac{V_{out}}{V_{in}}
\]

Measured values:

\[
Gain = \frac{1.67}{1.69} \approx 0.988 \approx 1
\]

---

## PCB Design

### PCB Stackup

- 4-layer PCB
- Dedicated ground plane
- RF trace optimization

### Design Parameters

| Parameter | Value |
|-----------|-------|
| Dielectric Constant (\( \epsilon_r \)) | 4.3 |
| Frequency | 2.45 GHz |
| Copper Thickness | 0.035 mm |
| Substrate Height | 0.254 mm |

---

## PCB Optimization

### Challenges

Initial microstrip calculations resulted in:
- Trace width = 0.46 mm
- Difficult manufacturing constraints

### Solutions

- Switched to coplanar waveguide with ground
- Moved ground plane to Layer 3
- Increased effective substrate height
- Increased trace width to 2.47 mm

---

## PCB Design Rules

| Rule | Value |
|------|------|
| Minimum Clearance | 1 mm |
| Minimum Track Width | 2.47 mm |
| Copper-to-Edge Clearance | 0.5 mm |

---

## Simulation Results

### Gain Improvement

| Stage | Gain |
|------|------|
| Original Circuit | 0 dB |
| Improved Circuit | 12 dB |
| Optimized RF Stage | 22–34 dB |

---

## Why This Design is Suitable for BLE

### Low Power Features

- Single transistor operation at 3.3V
- Passive mixer consumes minimal DC power
- LC tuning improves gain without increasing current
- Efficient RF front-end architecture

### BLE Advantages

- Low energy consumption
- Compact PCB design
- RF frequency compatibility
- Improved signal amplification

---

## Software & Tools Used

- RF Simulation Software
- Fourier Analysis Tools
- PCB Design Software
- Circuit Analysis Tools

---

## Applications

- Bluetooth Low Energy (BLE) Devices
- Wireless Sensor Networks
- IoT Communication Systems
- Low-Power RF Systems
- Embedded Wireless Devices

---

## Contributors

- Nichole Klipper
- Albertine Byemba-Kilongo
- Sai Anirudh Godavarthi
- Karthik Dorepally

## Repository Structure

```bash
BLE_Receiver_Front_End_Design/
│
├── Presentation/
│   └── BLE_Receiver_Mixed_Signal_Final_Project.pptx
│
├── Circuit_Design/
│   ├── final_circuit.png
│
├── Simulations/
│   └── ac_response_simulation.png
│
├── PCB_Design/
|   ├── board_setup.png
│   ├── pcb_calculations.png
│   └── final_pcb_layout.png
│
└── README.md
```

---

## License

This project is intended for academic and educational purposes.
