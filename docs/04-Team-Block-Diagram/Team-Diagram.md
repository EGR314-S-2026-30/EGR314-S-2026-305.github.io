---
title: Block Diagram, Protocol, and Message Structure
---

## 1️⃣ Team Block Diagram Overview

![Subsystem](Team_305_Block_Diagram.drawio.svg)

# Message Type Table

| Message Type (uint16_t) | Description |
|--------------------------|-------------|
| 1  | Motor Control State Report |
| 2  | Motor Status Report |
| 3  | Camera Frame Data Packet |
| 4  | Camera Status Report |
| 5  | Gyroscope Data Report |
| 6  | LCD Display Data Report |
| 7  | LCD Status Report |
| 8  | Temperature Sensor Data Report |
| 9  | Light Sensor Data Report |
| 10 | Barometric Pressure Sensor Data Report |
| 11 | Humidity Sensor Data Report |
| 12 | Distance Sensor Data Report |
| 13 | System Status Report |
| 14 | System Error Code Report |
| 15 | Debug Message (String) |
| 16 | Heartbeat / Alive Signal |

# Message Type Structure

---

## Message Type 1 – Motor Control State Report

| Payload Byte | Type      | Description |
|--------------|----------|-------------|
| 1–2 | uint16_t | 1 |
| 3–4 | int16_t  | Left Motor Speed (PWM) |
| 5–6 | int16_t  | Right Motor Speed (PWM) |
| 7   | uint8_t  | Left Motor Direction (0=Rev,1=Fwd) |
| 8   | uint8_t  | Right Motor Direction |

---

## Message Type 2 – Motor Status Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 2 |
| 3–4 | uint16_t | Left Motor Current (mA) |
| 5–6 | uint16_t | Right Motor Current (mA) |
| 7 | uint8_t | Left Motor Status Code |
| 8 | uint8_t | Right Motor Status Code |

---

## Message Type 3 – Camera Frame Data Packet

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 3 |
| 3–4 | uint16_t | Frame ID |
| 5–6 | uint16_t | Packet Index |
| 7–8 | uint16_t | Total Packets in Frame |
| 9–58 | uint8_t[] | Image Data Chunk (50 bytes) |

---

## Message Type 4 – Camera Status Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 4 |
| 3 | uint8_t | Camera State (0=Off,1=Idle,2=Capturing) |
| 4–5 | uint16_t | Frame Width |
| 6–7 | uint16_t | Frame Height |
| 8 | uint8_t | Error Code |

---

## Message Type 5 – Gyroscope Data Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 5 |
| 3–6 | float | Angular Velocity X (rad/s) |
| 7–10 | float | Angular Velocity Y |
| 11–14 | float | Angular Velocity Z |

---

## Message Type 6 – LCD Display Data Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 6 |
| 3–58 | char[] | Display Text (Null-terminated, max 55 chars) |

---

## Message Type 7 – LCD Status Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 7 |
| 3 | uint8_t | LCD Power State |
| 4 | uint8_t | Backlight Level |
| 5 | uint8_t | Error Code |

---

## Message Type 8 – Temperature Sensor Data Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 8 |
| 3–6 | float | Temperature (°C) |

---

## Message Type 9 – Light Sensor Data Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 9 |
| 3–6 | float | Light Intensity (lux) |

---

## Message Type 10 – Barometric Pressure Sensor Data Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 10 |
| 3–6 | float | Pressure (Pa) |
| 7–10 | float | Estimated Altitude (m) |

---

## Message Type 11 – Humidity Sensor Data Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 11 |
| 3–6 | float | Relative Humidity (%) |

---

## Message Type 12 – Distance Sensor Data Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 12 |
| 3–6 | float | Distance (meters) |

---

## Message Type 13 – System Status Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 13 |
| 3 | uint8_t | System State |
| 4–7 | uint32_t | Uptime (ms) |
| 8–9 | uint16_t | Battery Voltage (mV) |

---

## Message Type 14 – System Error Code Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 14 |
| 3 | uint8_t | Subsystem ID |
| 4 | uint8_t | Error Code |

---

## Message Type 15 – Debug Message (String)

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 15 |
| 3–58 | char[] | Debug String (Null-terminated, max 55 chars) |

---

## Message Type 16 – Heartbeat / Alive Signal

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 16 |
| 3 | uint8_t | System State |
| 4 | uint8_t | Error Flag |
