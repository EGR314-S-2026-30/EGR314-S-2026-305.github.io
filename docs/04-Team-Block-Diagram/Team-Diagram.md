---
title: Block Diagram, Protocol, and Message Structure
---

# Environmental Sensor Messages

## Message Types

| Message Type | Byte 1-2 | Description |
|--------------|----------|------------|
| 4            | 0x04     | Environmental sensor reading (temperature, pressure, humidity) |
| 11           | 0x0B     | Environmental subsystem error code |
| 12           | 0x0C     | Environmental subsystem status code |
| 13           | 0x0D     | Environmental subsystem status message (string) |

## Message Structures

### Message Type 4 – Sensor Reading

| Byte | Data Type | Description |
|------|-----------|------------|
| 1-2  | uint16_t  | Message Type = 0x04 |
| 3    | uint8_t   | Sensor ID (0 = temperature, 1 = humidity, 2 = pressure) |
| 4-5  | int16_t   | Sensor value (scaled as needed, e.g., temperature ×100 for 2 decimals) |
| 6-61 | char      | Optional telemetry string (e.g., `unit=Celsius`, `unit=hPa`) |

**Example:** Sending 23.56 °C from temperature sensor:

- Byte 3 = 0 (temperature)  
- Byte 4-5 = 2356  

### Message Type 12 – Subsystem Status Code

| Byte | Data Type | Description |
|------|-----------|------------|
| 1-2  | uint16_t  | Message Type = 0x0C |
| 3    | uint8_t   | Status code (0 = OK, 1 = calibration needed, 2 = sensor fault) |

### Message Type 13 – Subsystem Status Message

| Byte | Data Type | Description |
|------|-----------|------------|
| 1-2  | uint16_t  | Message Type = 0x0D |
| 3-58 | char      | Status message (max 55 characters, null-terminated) |

**Example:** `"Temp sensor OK"` → send as ASCII characters, final byte = `0x00`  

### Message Type 11 – Subsystem Error Code

| Byte | Data Type | Description |
|------|-----------|------------|
| 1-2  | uint16_t  | Message Type = 0x0B |
| 3    | uint8_t   | Error code (1 = temperature sensor fail, 2 = humidity sensor fail, 3 = pressure sensor fail) |
