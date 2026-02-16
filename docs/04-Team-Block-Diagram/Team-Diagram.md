---
title: Block Diagram, Protocol, and Message Structure
---

## 1️⃣ Team Block Diagram Overview

![Subsystem](block_diagram.png)

# Environmental Sensor Subsystem Specification
**Subsystem Designer:** Isaiah LaCombe  
This document defines the message types, byte-level structures, and hardware-to-message mapping for the Environmental Sensor Subsystem.

## Environmental Sensor Message Types & Structures

| Message Type | Byte(s)   | Data Type  | Description |
|--------------|-----------|-----------|-------------|
| 4 – Sensor Reading | 1-2       | uint16_t  | Message Type = 0x04 |
| 4 – Sensor Reading | 3         | uint8_t   | Sensor ID: 0 = Temperature, 1 = Humidity, 2 = Pressure |
| 4 – Sensor Reading | 4-5       | int16_t   | Sensor value (scaled, e.g., temperature ×100 for 2 decimals) |
| 4 – Sensor Reading | 6-61      | char      | Optional telemetry string, null-terminated (e.g., `"unit=Celsius"`, `"unit=hPa"`) |
| 11 – Subsystem Error | 1-2    | uint16_t  | Message Type = 0x0B |
| 11 – Subsystem Error | 3       | uint8_t   | Error code: 1 = temperature sensor fail, 2 = humidity sensor fail, 3 = pressure sensor fail |
| 12 – Subsystem Status Code | 1-2 | uint16_t | Message Type = 0x0C |
| 12 – Subsystem Status Code | 3   | uint8_t  | Status code: 0 = OK, 1 = calibration needed, 2 = sensor fault |
| 13 – Subsystem Status Message | 1-2 | uint16_t | Message Type = 0x0D |
| 13 – Subsystem Status Message | 3-58 | char   | Status message, max 55 characters, null-terminated |
