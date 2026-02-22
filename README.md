# Tiny-Nixie-Flyback-Converter
### Galvanically isolated multi-output flyback converter, specifically designed for Nixie clocks to ensure safe operation.

# Table of Contents
- [Project Overview](#project-overview)
- [Simulating with SIMPLIS](#simulating-with-simplis)
  - [Simulation model](#simulation-model)
  - [Transient simulation](#transient-simulation)
  - [Open loop Transfer function)](#open-loop-transfer-function)
  - [Closed loop Transfer function)](#closed-loop-transfer-function)
  - [No-Load Closed loop Transfer function)](#no-load-closed-loop-transfer-function)
- [Designed with Altium Designer](#designed-with-altium-designer)
  - [Schematic](#schematic)
  - [4-layer PCB](#4-layer-pcb)
- [Custom Designed Transformer](#custom-designed-transformer)
- [Measurements](#measurements)

# Project Overview
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

# Designed with Altium Designer
## Schematic
![schematic](pictures/schematic.png)
## 4-layer PCB
PCB Size: 30 mm X 37 mm

![pcb](pictures/pcb.png)

# Custom Designed Transformer
The power supply also includes a custom-designed flyback transformer on an EFD-15/8/5 core. The winding layers are arranged in a sandwich configuration. 
Key parameters:

- $N_p$ / $N_{s1}$ = 7/56
- $N_p$ / $N_{s2}$ = 7/3
- $L_p$ = 2.483 uH
- $L_{p.leak}$ = 43 nH
- $L_{s1.leak}$ = 3.12 uH
- $B_{max}$ < 0.1 T
- $P_{loss}$ < 0.2 W

![Transformer](pictures/transformer.png)


# Assembled PCB
![Assembled_PCB](Assembled_PCB/pcb2.png)

# Measurements
## Startup Under Full Load Conditions
![startup](Measurements/Tiny_startup.png)

## MOSFET gate measurements
The MOSFET gate waveform shows neither overshoot nor ringing. The gate resistor appears to be optimal.

![gate](Measurements/Tiny_gate.png)

## SW Node measurements (Mosfet drain measurements)
The SW node shows minimal overshoot at full load condition, with no ringing observed. The low-frequency oscillation is characteristic of DCM operation.

![sw_node](Measurements/Tiny_drain2.png)

## Secondary waveforms
The secondary of the transformer exhibits some ringing when the primary MOSFET turns on. 
The diode snubber circuit must be tuned. To do this, I measured the ringing frequency without the snubber, which was 18.52 MHz.

![secondary](Measurements/secunder_ringing.png)

![ringing](Measurements/Secunder_ringing_freq.png)

## Step Load Measurement
I also measured the step load response of the converter. 
The pictures below shows the response when the load steps from 10 mA to 20 mA. No ringing is observed.

![step1](Measurements/Step_load_meas1.png)

![step2](Measurements/Step_load_meas2.png)

## Output Ripple at full load
The measured output ripple meets the design requirements.

![ripple](Measurements/output_ripple.png)

## Efficiency of the converter
The figure below shows the efficiency of the converter at 5 V, 9 V, and 12 V input voltages.

![eff](Measurements/Tiny_Nixie_Flyback_Effficiency.png)

