---
title: Block Diagram, Protocol, and Message Structure
---

## 1️⃣ Team Block Diagram Overview

![Subsystem](block_diagram.png)

# Part 3: Environmental Sensor Board Message Types

| Message Type | Bytes | Data Description |
|--------------|-------|-----------------|
| 1 | 1-2 (uint16_t) | Temperature Reading (°C × 100, int16_t) |
| 2 | 1-2 (uint16_t) | Humidity Reading (%RH × 100, uint16_t) |
| 3 | 1-2 (uint16_t) | Barometric Pressure (Pa ÷ 10, uint16_t) |
| 4 | 1-2 (uint16_t) | Light Intensity (lux, uint16_t) |
| 5 | 1-2 (uint16_t) <br> 3-4 (uint16_t) | Sensor Calibration Command (sensor ID, calibration value) |
| 6 | 1-2 (uint16_t) <br> 3-58 (char) | Status Message / Error Message (null-terminated string) |

## Message Structure Examples

**Message Type 1 – Temperature Reading**  
| Byte | Description |
|------|-------------|
| 1-2 | 0x01 (Message Type ID) |
| 3-4 | Temperature ×100 (int16_t, big-endian) |

**Message Type 5 – Sensor Calibration Command**  
| Byte | Description |
|------|-------------|
| 1-2 | 0x05 (Message Type ID) |
| 3-4 | Sensor ID (uint16_t) |
| 5-6 | Calibration Value (uint16_t, big-endian) |

**Message Type 6 – Status/Error Message**  
| Byte | Description |
|------|-------------|
| 1-2 | 0x06 (Message Type ID) |
| 3-58 | ASCII string, null-terminated |

