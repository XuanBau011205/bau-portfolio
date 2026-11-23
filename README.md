# Doan Xuan Bau | Embedded Systems Portfolio

Electronics and Telecommunications Engineering Student at Hanoi University of Science and Technology (HUST).

Focus areas: Embedded Firmware, IoT, Industrial IoT (IIoT), and Edge AI.

[Tiếng Việt](README.vi.md)

## Projects

### 1. IoT Telemetry System

Role: Team Leader (3 members) - ESP32 firmware and data protocol design.

Technologies: ESP32-S3, C/C++, PlatformIO, MQTT, Spring Boot, PostgreSQL.

Key contributions:
- Built non-blocking FSM firmware using System Tick Timer.
- Implemented sensor sampling and digital filtering for MQ2 and DHT11.
- Designed a 16-byte binary communication protocol with CRC.
- Configured MQTT Last Will and Testament (LWT) for disconnect detection.
- Built a Spring Boot and PostgreSQL backend for telemetry storage and REST APIs.

Repositories:
- [Firmware - IoT Telemetry](https://github.com/XuanBau011205/IoT-Telemetry)
- [Backend - IoT Telemetry Backend](https://github.com/XuanBau011205/IoT-TelemetryBackend)

### 2. Single-Lead Battery-Powered ECG & On-Device HRV Monitor (P05)

Status: Hardware Gate G1 and G2 completed (ERC = 0, DRC = 0, Gerber/BOM ready). Firmware and Python simulation in progress.

Role: Team Leader (3 members) - Mixed-signal hardware design (schematic and 2-layer PCB), firmware architecture, and virtual board simulation.

Technologies: STM32F103C8T6, AD8232, INA219, Altium Designer (2-layer PCB), C (Q15 DSP), Python.

| Top Layer (80 x 55 mm, 4-zone layout) | Bottom Layer (Solid GND plane >90%, 125 stitching vias) |
| :---: | :---: |
| <img src="https://raw.githubusercontent.com/XuanBau011205/stm32-single-lead-ecg-hrv/main/docs/images/pcb_top.png" alt="P05 ECG PCB Top Layer" width="380" /> | <img src="https://raw.githubusercontent.com/XuanBau011205/stm32-single-lead-ecg-hrv/main/docs/images/pcb_bottom.png" alt="P05 ECG PCB Bottom Layer" width="380" /> |

Key contributions:
- Completed schematic capture and custom IPC-7351 component libraries in Altium Designer (91 components, ERC = 0 errors, 0 warnings).
- Laid out an 80.0 x 55.0 mm 2-layer mixed-signal PCB (DRC = 0 violations) separating the Analog AFE zone (AD8232) from Digital/Power zones, with an unbroken >90% bottom GND plane, 125 stitching vias, 0-via symmetric differential ECG traces, and isolated 8 MHz / 32.768 kHz crystals.
- Designed a low-power supply tree targeting 32.1 uA in Stop Mode: USB-C 5V Li-ion charging (MCP73831), MCP1700-3.3V LDO, INA219 I2C current monitor with PPK2 header (J_IMEAS), AO3401 P-MOSFET microSD power gating, and 2N7002 switched battery divider.
- Wrote Altium DelphiScripts for collision-free placement, critical analog/crystal routing, and DRC/silkscreen cleanup; exported fabrication files verified on JLCPCB Gerber Viewer (Gerber RS-274X, PTH/NPTH/Slot NC Drill, BOM, Pick-and-Place).
- Set up a zero-heap CMake firmware structure (Q15 DSP, parabolic R-peak interpolation, Ping-Pong DMA) and implemented Phase 1 and Phase 3 of the Python virtual board twin (physical hardware models + Unicorn ARM Cortex-M3 + STM32F103 MMIO, 7/7 unit tests passing).

Repository:
- [P05 STM32 Single-Lead ECG & HRV](https://github.com/XuanBau011205/stm32-single-lead-ecg-hrv)

## Technical Interests

- Embedded Firmware Development
- Industrial IoT (IIoT)
- Microcontroller-based Signal Processing
- Edge AI
