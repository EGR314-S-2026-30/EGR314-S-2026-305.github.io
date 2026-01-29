---
title: Project Requirements
---

# Overview and Rationale

Through team discussions, we have refined our rover design to focus on **modular exploration of a simulated Martian environment**. The rover is **remotely operated** and collects scientific and environmental data through a variety of sensors, including:

- Atmospheric pressure  
- Temperature and humidity (weather-related)  
- Hazard/obstacle detection  
- Imaging (camera)  
- Navigation/orientation sensors (IMU, odometry)

The rover features 2-wheel drive with steering, with 4-wheel drive as a possible future enhancement. Most structural components (chassis, mounts, body) will be **3D printed** for rapid prototyping and customization. Non-printable components, such as wheels, motors, electronics, and sensors, will be purchased off-the-shelf.

The rover operates over a daisy-chain UART network with 8-wire ribbon cables connecting all modular subsystem boards. Each board is independently controlled but communicates via a shared protocol. Remote operation is achieved through bidirectional wireless communication, allowing real-time telemetry, video streaming, and manual control from a base station.

This approach emphasizes:

- Open-ended exploration: Real-time scientific data collection rather than fixed mission tasks  
- Subsystem modularity: Individual boards for mobility, sensors, HMI, and communication  
- Reliable integration: Daisy-chain UART network ensures safe message passing between boards  
- Safety and durability: Emergency stop, fail-safes, and low-power operation mirror real planetary rover practices  

## Key Feature-to-Requirement Mappings

| Feature | Requirement |
|---------|------------|
| Mobility | 2WD with steering required for controllable movement across simulated Martian terrain. 4WD may be added for enhanced capability. |
| Scientific exploration | Dedicated sensors for pressure, temperature/humidity, and navigation enable environmental data collection. |
| Hazard avoidance | Obstacle detection protects the rover during remote operation when direct visual cues are limited. |
| Imaging and feedback | Camera and real-time telemetry provide the operator with situational awareness. |
| Remote teleoperation | Wireless link enables driving commands and streams sensor/video data back to the base station. |
| Construction and constraints | 3D-printed structure with purchased components, plus power and safety constraints that affect all subsystems. |
| Modular subsystem integration | All boards communicate via UART in a daisy-chain configuration for reliability and expansion. |

## Requirements Table

| Description | Minimum (Acceptance – Not Complete Failure) | Target | Feature Satisfied | Stretch? |
|------------|--------------------------------------------|-------|-----------------|----------|
| Rover shall provide drive mobility with independent motor control | Forward/backward movement on flat surfaces ≥0.1 m/s | 2WD with variable speed (0.1–0.5 m/s); 4WD optional | Mobility (Drive) | Yes (4WD) |
| Rover shall implement steering control for directional navigation | Basic turning via differential drive or simple servo steering | Precise steering with ≥30° turn radius | Mobility (Steering) | No |
| Rover shall detect obstacles/hazards and alert or autonomously slow/stop | Detect obstacles ≤0.5 m ahead using ultrasonic/IR sensors with operator alert | Detection ≤1.5 m, proportional speed reduction or auto-stop | Hazard Avoidance, Safety | No |
| Rover shall measure atmospheric pressure | Functional barometric sensor reporting values in real-time | Calibrated sensor (0–1100 hPa) streaming to base | Environmental Sensing (Pressure) | No |
| Rover shall measure temperature and humidity | Basic temperature (±2°C) and RH sensor functional | High-accuracy (±0.5°C, ±3% RH) with real-time streaming | Environmental Sensing (Weather) | No |
| Rover shall provide navigation/orientation data | Basic IMU/compass for heading and tilt | 6/9-DOF IMU with odometry integration for dead-reckoning | Navigation | No (full dead-reckoning is stretch) |
| Rover shall capture and stream imaging data | Static image capture on demand | Real-time low-latency video feed (≥10 fps) | Imaging, Operator Feedback | Yes |
| Two-way wireless communication shall enable remote control and telemetry | Basic command transmission and sensor return within 15 m | <300 ms latency, simultaneous control + multi-sensor/video streaming | Remote Teleoperation, Feedback | No |
| Base station HMI shall display real-time sensor data and vehicle status | Text/numeric display of sensors and battery | Graphical dashboard with camera view, alerts, and data logging | Operator Feedback, HMI | No |
| Rover chassis and major structural components shall be 3D printed | Primary structure printable and assembled with purchased parts | Optimized lightweight design, durable filament, survives repeated drops | Construction (3D Printed) | No |
| Power system shall support extended operation | ≥30 minutes continuous operation | ≥90 minutes, low-power modes, real-time battery monitoring | System Constraint (Power) | No |
| System shall include emergency stop and fail-safe behaviors | Software/commanded stop of all motors on signal loss or e-stop | Automatic safe state on communication loss (stop + status broadcast) | Safety, Durability | No |

## Requirement Assignment to Team Members

| Requirement Description | Primary Assignee (Functional Area) |
|------------------------|----------------------------------|
| Drive mobility (2WD/4WD optional) | Sensor & Actuator Control Board |
| Steering control | Sensor & Actuator Control Board |
| Obstacle detection / hazard avoidance | Sensor & Actuator Control Board |
| Atmospheric pressure measurement | Environmental Sensor Board |
| Temperature & humidity measurement | Environmental Sensor Board |
| Navigation/orientation data | Navigation Board |
| Imaging capture and streaming | Imaging Board |
| Two-way wireless communication | Wireless Communication Board |
| Base station HMI | HMI Board |
| 3D-printed chassis & structural components | System Integration & Safety |
| Power system | System Integration & Safety |
| Emergency stop / fail-safe | System Integration & Safety |

**Notes on Alignment with Semester Requirements:**

- Rover is modular, with each team member owning a **subsystem board**.  
- 2WD is primary, with 4WD as a potential stretch goal.  
- Radiation sensing has been removed to simplify subsystem requirements.  
- All boards communicate safely over the UART daisy-chain network.  
- Subsystems include sensors, actuators, HMI, and wireless communication**, meeting course modularity requirements.  
