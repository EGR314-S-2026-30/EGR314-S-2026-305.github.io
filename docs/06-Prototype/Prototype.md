# Prototype System

## Overview

The initial prototype was designed as a distributed embedded system consisting of seven independent ESP32-based subsystems. Each board handled a specific sensor, actuator, or communication task.

All boards were connected using ribbon cables and communicated via UART (RX/TX), allowing data transfer between subsystems without a central controller.

## Prototype Setup
<img width="3024" height="4032" alt="IMG_0783" src="https://github.com/user-attachments/assets/abed6802-afb8-4d17-8a05-0863d14faf40" />



---

## System Architecture

The prototype included the following subsystems:

- Distance Sensor (Time-of-Flight)
- Temperature Sensor
- Camera Module
- Motor Control System
- LCD Display
- MQTT Communication Module
- Power Distribution

Each subsystem operated independently while sharing data across the system.

---

## Communication

UART was used for communication between boards:

- TX → RX connections between subsystems  
- Common ground shared across all boards  

Ribbon cables were used for flexible connections during testing and integration.

---

## Power Distribution

All boards were powered from a shared source, with local regulation to 5V and 3.3V on each subsystem.

Power stability became a key issue during integration, especially with multiple active boards.

---

## Challenges

**ESP32 Flashing**
- Inconsistent firmware uploads  
- Boot mode and connection issues  

**Communication**
- Data inconsistencies between boards  
- Difficulty managing multiple UART connections  

**Sensor Integration**
- Devices detected but not returning valid data  
- Pin configuration and communication conflicts  

**Power**
- Voltage drops across the system  
- Unstable behavior under load  

---

## Key Takeaways

- Reliable communication requires structured design  
- Power distribution is critical in multi-board systems  
- Hardware and firmware debugging must be done together  
- System integration introduces complexity beyond individual subsystems  

---

## Transition to Final Design

These challenges led to improvements in communication structure, power stability, and overall system integration for the final design.
