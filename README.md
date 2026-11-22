# Đoàn Xuân Báu | Embedded Systems Portfolio

Electronics and Telecommunications Engineering Student at Hanoi University of Science and Technology (HUST).

Interested in Embedded Firmware, IoT, Industrial IoT (IIoT), and Edge AI.

[Tiếng Việt](README.vi.md)

## Projects

### 1. IoT Telemetry System

**Role:** Team Leader (3 members) - ESP32 Firmware & Data Protocol Design

**Technologies:** ESP32-S3, C/C++, PlatformIO, MQTT, Spring Boot, PostgreSQL.

**Key Contributions:**
- Developed non-blocking FSM firmware using System Tick Timer.
- Implemented sensor sampling and digital filtering for MQ2 and DHT11.
- Designed a 16-byte binary communication protocol with CRC.
- Implemented MQTT Last Will and Testament (LWT).
- Developed a Spring Boot and PostgreSQL backend for telemetry storage and REST API integration.

**Repositories:**
- [Firmware -  IoT Telemetry](https://github.com/XuanBau011205/IoT-Telemetry)
- [Backend -  IoT Telemetry Backend](https://github.com/XuanBau011205/IoT-TelemetryBackend)

### 2. Single-Lead Battery-Powered ECG & On-Device HRV Monitor (P05)

**Status:** Hardware Gate G1 & G2 Completed (`ERC = 0`, `DRC = 0`, Gerber/BOM Ready) — Firmware & Digital Twin In Progress

**Role:** Team Leader (3 members) — Mixed-Signal Hardware Design (Schematic + 2-Layer PCB), Firmware Architecture & Simulation

**Technologies:** STM32F103C8T6, AD8232, INA219, Altium Designer (2-Layer PCB), C (Q15 DSP), Python.

| Top Layer (`80 × 55 mm`, 4-Zone Layout) | Bottom Layer (Solid GND Plane >90% + 125 Stitching Vias) |
| :---: | :---: |
| <img src="https://raw.githubusercontent.com/XuanBau011205/stm32-single-lead-ecg-hrv/main/docs/images/pcb_top.png" alt="P05 ECG PCB Top Layer" width="380" /> | <img src="https://raw.githubusercontent.com/XuanBau011205/stm32-single-lead-ecg-hrv/main/docs/images/pcb_bottom.png" alt="P05 ECG PCB Bottom Layer" width="380" /> |

**Key Contributions:**
- Completed full schematic capture and IPC-7351 component libraries (**91 components, `ERC = 0 Errors, 0 Warnings`**).
- Designed a compact **`80.0 × 55.0 mm` 2-layer mixed-signal PCB (`DRC = 0 Violations`)** with strict Analog/Digital spatial partitioning, >90% unbroken bottom GND plane, 125 stitching vias, symmetric 0-via differential ECG routing, and isolated 8 MHz / 32.768 kHz crystals.
- Engineered an ultra-low-power supply architecture (`32.1 µA` Stop Mode target) with `MCP73831` USB-C charging, `MCP1700` LDO, `INA219` current monitor + `J_IMEAS` PPK2 header, `AO3401` microSD power-gating, and `2N7002` switched battery divider.
- Automated placement, critical analog/crystal pre-routing, and DRC/silkscreen cleanup via Altium DelphiScripts; generated factory-verified **JLCPCB Gerber RS-274X, NC Drill (PTH/NPTH/Slot), BOM, and Pick-and-Place** packages.
- Architected a zero-heap CMake firmware pipeline (`Q15` DSP + parabolic R-peak interpolation + Ping-Pong DMA) and a **Python Virtual Hardware Twin (`P05-Sim`)** architecture.

**Repository:**
- [P05 STM32 Single-Lead ECG & HRV](https://github.com/XuanBau011205/stm32-single-lead-ecg-hrv)

## Technical Interests

- Embedded Firmware Development
- Industrial IoT (IIoT)
- Microcontroller-based Signal Processing
- Edge AI
