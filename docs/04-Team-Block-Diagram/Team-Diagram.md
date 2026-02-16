---
title: Block Diagram, Protocol, and Message Structure
---
# Rover Block Digram Project Overview

## Project and Block Digram Overview
Through team discussions, we designed our rover to explore a simulated Martian environment. The rover is remotely operated and collects scientific and environmental data through a variety of sensors, including:

- Atmospheric pressure
- Temperature and humidity
- Hazard detection
- Imaging
- Navigation/orientation (IMU and odometry)

Mobility is provided by a 2-wheel drive with steering, with 4-wheel drive considered as a future enhancement. Most structural components (chassis, mounts, body) are 3D printed for rapid prototyping, while wheels, motors, electronics, and sensors are purchased.  

Subsystems communicate via a daisy-chained UART network and over WiFi, allowing independent boards to send and receive messages safely. Remote operation is achieved through bidirectional wireless communication for real-time telemetry, video streaming, and manual control. A local Human–Machine Interface (HMI) consisting of pushbuttons, levers, and an OLED display provides immediate system feedback without requiring remote connection.

## Project Rationale
The rover is designed as an open-ended exploration platform, focused on collecting real-time scientific data rather than performing fixed tasks. Key design aspects include:

- Modular Setup: Separate sensor, actuator, HMI, and communication boards connected via a daisy-chained UART network.  
- Real-Time Monitoring: Local OLED display allows users to monitor data and adjust settings.  
- Safety Features: Emergency stop, built-in fail-safes, and low-power operation reflect real planetary rover design considerations.

## Key Feature-to-Requirement Mappings
| Feature | Requirement |
|---------|------------|
| Mobility | 2WD with steering; stretch goal: 4WD |
| Scientific Exploration | Sensors for pressure, temperature, humidity, and navigation with calibrated real-time telemetry |
| Hazard Avoidance | Obstacle detection and alerts; optional automatic slow/stop |
| Imaging & Feedback | Camera/video streaming for situational awareness |
| User Interaction | Local OLED display and input buttons for redundancy |
| Modular Subsystem Integration | Reliable UART communication; allows future expansion |
| Safety & Power Management | Emergency stop, fail-safes, low-power operation |

## Requirements Table
| Description | Minimum | Target | Feature Satisfied |
|------------|--------|--------|----------------|
| Rover shall provide drive mobility with independent motor control | Forward/backward ≥0.1 m/s | 2WD with variable speed (0.1–0.5 m/s) | Mobility (Drive) |
| Rover shall implement steering control | Basic turning using differential drive | Controlled steering ≥30° turning radius | Mobility (Steering) |
| Rover shall detect obstacles or hazards | Detect ≤0.5 m ahead | Detect ≤1.5 m with optional auto slow/stop | Hazard Avoidance, Safety |
| Rover shall measure atmospheric pressure | Functional barometric sensor | Calibrated 0–1100 hPa | Environmental Sensing (Pressure) |
| Rover shall measure temperature and humidity | ±2 °C, basic sensing | Continuous telemetry ±1 °C, ±5% RH | Environmental Sensing (Weather) |
| Rover shall provide navigation and orientation data | IMU heading and tilt | Optional wheel odometry integration | Navigation & Orientation |
| Rover shall capture and transmit imaging data | Capture static images | Real-time video ≥5 fps | Imaging & Operator Feedback |
| Two-way wireless communication | Commands reach rover | Stable Wi-Fi/Bluetooth link | Teleoperation & Wireless Communication |
| Rover shall provide local HMI | OLED shows basic status | Menu-driven OLED with data, alerts, parameters | HMI (OLED) |
| Chassis and structural components | Printable and assembleable | Lightweight, durable for testing | Mechanical Construction |
| Power system | ≥30 minutes operation | ~60 minutes with monitoring | Power Management |
| Emergency stop and fail-safe | Physical or software stop works | Automatic safe state, alerts | System Safety |
| Communication network | Occasional delays | Reliable UART/I2C messaging | Modular Subsystem Integration |
| Chassis weight limit | ≤5 kg | ≤4.5 kg for efficiency | Mechanical Construction & Mobility |
| Maximum current draw | ≤2 A per subsystem | ≤1.5 A per subsystem | Power Management & Safety |
| Environmental tolerance | Functional indoors | Functional outdoors 0–40°C, 20–80% RH | Environmental Sensing & Safety |

## Requirement Assignment to Team Members
| Member | Name | Key Responsibilities | Primary Subsystem |
|--------|------|-------------------|-----------------|
| 1 | Liam Mabbutt | Rover drive mobility: 2WD baseline, 4WD optional, motor speed/steering control, feedback, safety interlocks | Mobility & Motor Control Board |
| 2 | Myles White | Obstacle/hazard detection, collision warnings, autonomous slow/stop, safety alerts | Obstacle Detection & Safety Board |
| 3 | Isaiah Lacombe | Environmental sensing: pressure, temperature, humidity, calibration, real-time telemetry | Environmental Sensor Board |
| 4 | Ragul Raj RG | Navigation & orientation: IMU, optional wheel odometry, heading, tilt, motion reporting | Navigation & Orientation Board |
| 5 | Arianna Lazaritt | Imaging system: camera control, image/video capture, data packetization, status reporting | Imaging Board |
| 6 | Damian Novgorodov | Two-way wireless communication (Wi-Fi/Bluetooth), command routing, telemetry aggregation, system messaging | Wireless Communication Board |
| 7 | Christo Jomon Joseph | Local HMI: OLED display, pushbuttons, rover status, user input, power monitoring, emergency stop, fail-safes | HMI & System Safety Board |
