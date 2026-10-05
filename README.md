# Circuit-Design

Embedded Systems & IoT (Aug - Nov 2026) - Lab Exercise: Schematics with ESP32

## Part A - Calculations
- `PartA_Calculations.pdf` - total resistance, total current, and the current, voltage drop and power for each resistor, for both circuits.

| Circuit | Total R | Total I | Total P |
|---|---|---|---|
| (a) Series 20 + 30 + 50 ohm, 125 V | 100 ohm | 1.25 A | 156.25 W |
| (b) Parallel 20 // 100 // 50 ohm, 125 V | 12.5 ohm | 10 A | 1250 W |

## Part B - Schematics (EasyEDA Pro)
The EasyEDA project `Circuit-Design` has one schematic per circuit: `Schematic1` (circuit a), `circuite_b_parallel` (circuit b) and `ESP32_DHT22`.

- `PartB1_Circuit_a_Series_Schematic.pdf` - circuit (a) schematic
- `PartB1_Circuit_b_Parallel_Schematic.pdf` - circuit (b) schematic
- `PartB2_ESP32_DHT22_Schematic.pdf` - ESP32-WROOM-32 + DHT22 schematic
- `images/` - the same schematics as PNG images
- `component_lists/` - the component list for each schematic (CSV)

### ESP32 + DHT22 design summary
- 5 V input (J1) -> AMS1117-3.3 (U2) -> 3.3 V rail (C1 10 uF in, C2 22 uF + C3 100 nF out)
- DHT22 (U3) powered from 3.3 V (sensor supply range 3.3 - 5 V), 100 nF decoupling (C5)
- DHT22 DATA -> ESP32 GPIO4 with 10 k pull-up (R2)
- EN: 10 k pull-up (R1) + 1 uF (C4) reset delay, reset button SW1; BOOT button SW2 on IO0
- UART header J2 (3V3, TXD0, RXD0, GND) for programming
