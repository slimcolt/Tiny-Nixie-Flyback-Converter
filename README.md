# Tiny-Nixie-Flyback-Converter
### Galvanically isolated multi-output flyback converter, specifically designed for Nixie clocks to ensure safe operation.

## Project Overview
The power supply provides full galvanic isolation for the Nixie tubes and their control circuitry.
Technical specifications of the power supply:
- Input voltage range: 4.5 V – 13 V
- Output voltage 1: 170 V (for the Nixie tubes)
- Output voltage 2: 3.3 V (for the control circuitry)
- Output current 1: 20 mA
- Output current 2: 50 mA
- Maximum duty cycle: 0.85
- Switching frequency: 300 kHz
- Current-mode control without slope compensation
- Type II compensation
- Galvanic isolation of feedback using an opto-emulator
- Custom EFD-15 transformer
- 100% DCM operation
- Hiccup-mode overcurrent protection
- Soft start
- UVLO

# Table of Contents
- [Simulating with SIMPLIS](#simulating-with-simplis)
  - [Simulation model](#simulation-model)
  - [Transient simulation](#transient-simulation)
  - [Open loop Transfer function)](#open-loop-transfer-function)
  - [Closed loop Transfer function)](#closed-loop-transfer-function)
  - [No-Load Closed loop Transfer function)](#no-load-closed-loop-transfer-function)

- [The circuit was designed in Altium Designer](#the-circuit-was-designed-in-altium-designer)
  - [Schematic](#schematic)
  - [4-layer PCB](#4-layer-pcb)

# Simulating with SIMPLIS
## Simulation model
![Simplis](pictures/simplis_model.png)
## Transient simulation
$U_i$ = 5 V @ full load

![Simplis](pictures/transient_simulation.png)
## Open loop Transfer function
$U_i$ = 5 V @ full load

![Open_Loop_TF](pictures/open_loop_png.png)
## Closed loop Transfer function
$U_i$ = 5 V @ full load

![Closed_Loop_TF](pictures/closed_loop_png.png)
## No-Load Closed loop Transfer function
$U_i$ = 5 V @ no load

![Closed_Loop_TF_noload](pictures/closed_loop_no_load.png)

# The circuit was designed in Altium Designer
## Schematic
![schematic](pictures/schematic.png)
## 4-layer PCB
![pcb](pictures/pcb.png)

