# Đoàn Xuân Báu | Portfolio Embedded Systems

Sinh viên ngành Kỹ thuật Điện tử - Viễn thông tại Đại học Bách khoa Hà Nội (HUST).

Quan tâm đến Embedded Firmware, IoT, Industrial IoT (IIoT) và Edge AI.

[English](README.md)

## Các dự án

### 1. Hệ thống giám sát và thu thập dữ liệu IoT (IoT Telemetry System)

**Vai trò:** Trưởng nhóm (3 thành viên) - Phụ trách firmware ESP32 và thiết kế giao thức dữ liệu.

**Công nghệ:** ESP32-S3, C/C++, PlatformIO, MQTT, Spring Boot, PostgreSQL.

**Các đóng góp chính:**
- Phát triển firmware theo mô hình FSM non-blocking, sử dụng System Tick Timer.
- Triển khai lấy mẫu cảm biến và lọc số liệu cho MQ2 và DHT11.
- Thiết kế giao thức truyền dữ liệu nhị phân 16 byte kèm CRC.
- Cấu hình MQTT Last Will and Testament (LWT).
- Phát triển backend bằng Spring Boot và PostgreSQL để lưu trữ telemetry và tích hợp REST API.

**Repositories:**
- [Firmware - IoT Telemetry](https://github.com/XuanBau011205/IoT-Telemetry)
- [Backend - IoT Telemetry Backend](https://github.com/XuanBau011205/IoT-TelemetryBackend)

### 2. Thiết bị đo ECG một đạo trình & phân tích HRV chạy pin (P05)

**Trạng thái:** Hoàn thành Phần cứng Gate G1 & G2 (`ERC = 0`, `DRC = 0`, sẵn sàng đặt mạch) — Đang triển khai Firmware & Python Digital Twin.

**Vai trò:** Trưởng nhóm (3 thành viên) — Thiết kế Phần cứng (Schematic + PCB 2 lớp), Kiến trúc Firmware & Mô phỏng.

**Công nghệ:** STM32F103C8T6, AD8232, INA219, Altium Designer (PCB 2 lớp), C (Q15 DSP), Python.

| Mặt Top (`80 × 55 mm`, phân 4 vùng) | Mặt Bottom (GND liền khối >90% + 125 Stitching Vias) |
| :---: | :---: |
| <img src="https://raw.githubusercontent.com/XuanBau011205/stm32-single-lead-ecg-hrv/main/docs/images/pcb_top.png" alt="P05 ECG PCB Top Layer" width="380" /> | <img src="https://raw.githubusercontent.com/XuanBau011205/stm32-single-lead-ecg-hrv/main/docs/images/pcb_bottom.png" alt="P05 ECG PCB Bottom Layer" width="380" /> |

**Các đóng góp chính:**
- Hoàn thiện sơ đồ nguyên lý và bộ thư viện chuẩn IPC-7351 trên Altium Designer (**91 linh kiện, `ERC = 0 Errors, 0 Warnings`**).
- Thiết kế **PCB 2 lớp `80.0 × 55.0 mm` (`DRC = 0 Violations`)**: tách biệt chặt vùng Analog AFE (`AD8232`) và vùng Digital (`STM32`, `SPI1`, `Power`), mặt GND đáy liền khối >90% kèm 125 stitching vias, đi dây vi sai ECG đối xứng (0 via) và bảo vệ thạch anh `8 MHz / 32.768 kHz`.
- Thiết kế chuỗi nguồn siêu tiết kiệm năng lượng (`Stop Mode = 32.1 µA`): sạc Li-ion `MCP73831`, LDO `MCP1700`, đo dòng `INA219` + header PPK2 `J_IMEAS`, ngắt nguồn microSD bằng `AO3401` và cầu đo pin bằng `2N7002`.
- Tự động hóa bố trí linh kiện, đi dây tín hiệu nhạy cảm và dọn lỗi DRC/silkscreen bằng Altium DelphiScript; xuất đầy đủ bộ file gia công kiểm chứng trên **JLCPCB Gerber Viewer** (Gerber RS-274X, NC Drill, BOM, Pick-and-Place).
- Xây dựng khung firmware CMake zero-heap (`Q15` DSP + nội suy Parabol + Ping-Pong DMA) và kiến trúc **Python Digital Twin (`P05-Sim`)**.

**Repository:**
- [P05 STM32 Single-Lead ECG & HRV](https://github.com/XuanBau011205/stm32-single-lead-ecg-hrv)

## Lĩnh vực kỹ thuật quan tâm

- Phát triển Embedded Firmware.
- Industrial IoT (IIoT).
- Xử lý tín hiệu trên nền tảng vi điều khiển.
- Edge AI.
