# Đoàn Xuân Báu | Portfolio Embedded Systems

Sinh viên ngành Kỹ thuật Điện tử - Viễn thông tại Đại học Bách khoa Hà Nội (HUST).

Lĩnh vực quan tâm: Embedded Firmware, IoT, Industrial IoT (IIoT) và Edge AI.

[English](README.md)

## Các dự án

### 1. Hệ thống giám sát và thu thập dữ liệu IoT (IoT Telemetry System)

Vai trò: Trưởng nhóm (3 thành viên) - Phụ trách firmware ESP32 và thiết kế giao thức dữ liệu.

Công nghệ: ESP32-S3, C/C++, PlatformIO, MQTT, Spring Boot, PostgreSQL.

Các đóng góp chính:
- Phát triển firmware theo mô hình FSM non-blocking, dùng System Tick Timer.
- Triển khai lấy mẫu cảm biến và lọc số cho MQ2 và DHT11.
- Thiết kế giao thức truyền dữ liệu nhị phân 16 byte kèm CRC.
- Cấu hình MQTT Last Will and Testament (LWT) để phát hiện mất kết nối.
- Xây dựng backend bằng Spring Boot và PostgreSQL để lưu telemetry và cung cấp REST API.

Mã nguồn:
- [Firmware - IoT Telemetry](https://github.com/XuanBau011205/IoT-Telemetry)
- [Backend - IoT Telemetry Backend](https://github.com/XuanBau011205/IoT-TelemetryBackend)

### 2. Thiết bị đo ECG một đạo trình và phân tích HRV chạy pin (P05)

Trạng thái: Hoàn thành phần cứng Gate G1 và G2 (ERC = 0, DRC = 0, đủ file đặt mạch). Đang triển khai firmware và mô phỏng Python.

Vai trò: Trưởng nhóm (3 thành viên) - Thiết kế phần cứng (schematic và PCB 2 lớp), kiến trúc firmware và mô phỏng bo ảo.

Công nghệ: STM32F103C8T6, AD8232, INA219, Altium Designer (PCB 2 lớp), C (Q15 DSP), Python.

| Mặt Top (80 x 55 mm, phân 4 vùng) | Mặt Bottom (GND liền khối >90%, 125 stitching vias) |
| :---: | :---: |
| <img src="https://raw.githubusercontent.com/XuanBau011205/stm32-single-lead-ecg-hrv/main/docs/images/pcb_top.png" alt="P05 ECG PCB Top Layer" width="380" /> | <img src="https://raw.githubusercontent.com/XuanBau011205/stm32-single-lead-ecg-hrv/main/docs/images/pcb_bottom.png" alt="P05 ECG PCB Bottom Layer" width="380" /> |

Các đóng góp chính:
- Hoàn thiện sơ đồ nguyên lý và bộ thư viện chuẩn IPC-7351 trên Altium Designer (91 linh kiện, ERC = 0 lỗi, 0 cảnh báo).
- Thiết kế PCB 2 lớp kích thước 80.0 x 55.0 mm (DRC = 0 vi phạm): tách riêng vùng Analog AFE (AD8232) và vùng Digital/Nguồn, mặt GND đáy liền khối >90% kèm 125 stitching vias, đi dây vi sai ECG đối xứng (0 via) và bảo vệ thạch anh 8 MHz / 32.768 kHz.
- Thiết kế mạch nguồn tiêu thụ thấp (mục tiêu Stop Mode 32.1 uA): sạc pin Li-ion qua USB-C 5V (MCP73831), LDO MCP1700-3.3V, đo dòng I2C INA219 kèm header PPK2 (J_IMEAS), ngắt nguồn microSD bằng P-MOSFET AO3401 và ngắt cầu đo pin bằng 2N7002.
- Viết Altium DelphiScript tự động bố trí linh kiện, đi dây vùng tín hiệu nhạy cảm và dọn lỗi DRC/silkscreen; xuất đủ bộ file gia công đã kiểm tra trên JLCPCB Gerber Viewer (Gerber RS-274X, NC Drill PTH/NPTH/Slot, BOM, Pick-and-Place).
- Xây dựng cấu trúc firmware CMake zero-heap (Q15 DSP, nội suy Parabol tìm đỉnh R, Ping-Pong DMA) và hoàn thành Phase 1, Phase 3 của bo mạch ảo Python (mô hình phần cứng + Unicorn ARM Cortex-M3 + STM32F103 MMIO, qua 7/7 bài test).

Mã nguồn:
- [P05 STM32 Single-Lead ECG & HRV](https://github.com/XuanBau011205/stm32-single-lead-ecg-hrv)

## Lĩnh vực kỹ thuật quan tâm

- Phát triển Embedded Firmware
- Industrial IoT (IIoT)
- Xử lý tín hiệu trên vi điều khiển
- Edge AI
