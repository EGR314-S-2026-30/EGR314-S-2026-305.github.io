---
title: Project Requirements
---

## Header
# Overview and Rationale

Through team discussions, we have refined the rover design to focus primarily on exploration of a simulated Martian environment. The rover will be remotely driven and will actively collect and transmit scientific and environmental data using a suite of sensors:

- Atmospheric pressure
- Temperature/humidity (weather-related)
- Radiation
- Hazard/obstacle detection
- Imaging (camera)
- Navigation/orientation sensors

The rover will feature a 4-wheel drive system with steering for robust mobility on uneven terrain. The majority of the structural components (chassis, mounts, body) will be 3D printed for rapid prototyping and customization, while non-printable parts (wheels, motors, electronics, sensors) will be purchased off-the-shelf.

Remote operation will be achieved through reliable two-way wireless communication, allowing manual control from a base station (laptop or dedicated controller) while streaming real-time sensor data, video/imaging, and system status back to the operator for teleoperation and data logging.

This exploratory focus shifts away from structured missions toward open-ended remote scientific data collection, emphasizing real-time feedback, sensor integration, and reliable mobility — qualities that mirror real planetary rover operations.

## Key Feature-to-Requirement Mappings

| Feature | Requirement |
|---------|------------|
| Mobility | 4-wheel drive and steering required for controllable movement across simulated Martian terrain (sand, rocks, inclines). |
| Scientific exploration | Dedicated sensors for pressure, temperature/humidity, radiation, and navigation enable environmental data collection. |
| Hazard avoidance | Obstacle detection protects the rover during remote operation when direct visual cues are limited. |
| Imaging and feedback | Camera and real-time telemetry provide the operator with situational awareness. |
| Remote teleoperation | Wireless link enables driving commands and streams sensor/video data back to the base station. |
| Construction and constraints | 3D-printed structure with purchased components, plus power and safety constraints that affect all subsystems. |

Requirements are distributed across team members to ensure each has primary ownership of critical functional areas.

# Requirements Table

| Description | Minimum (Acceptance – Not Complete Failure) | Target | Feature Satisfied | Stretch? |
|------------|--------------------------------------------|-------|-----------------|----------|
| Rover shall provide 4-wheel drive mobility with independent motor control | Basic forward/backward movement on flat surfaces at ≥0.1 m/s | All-wheel drive with variable speed (0.1–0.5 m/s), ability to climb ≥10° inclines and small obstacles | Mobility (4WD) | No |
| Rover shall implement steering control for directional navigation | Basic turning via differential drive or simple servo steering | Precise Ackermann or 4-wheel steering with ≥30° turn radius on uneven terrain | Mobility (Steering) | No |
| Rover shall detect obstacles/hazards and alert or autonomously slow/stop | Detection of obstacles ≤0.5 m ahead using ultrasonic/IR sensors with operator alert | Detection ≤1.5 m, proportional speed reduction or auto-stop, resume capability | Hazard Avoidance, Safety | No |
| Rover shall measure atmospheric pressure | Functional barometric sensor reporting values in real-time | Accurate readings (0–1100 hPa) with calibration and transmission to base station | Environmental Sensing (Pressure) | No |
| Rover shall measure temperature and humidity | Basic temperature (±2°C) and relative humidity sensor functional | High-accuracy (±0.5°C, ±3% RH) with real-time data streaming | Environmental Sensing (Weather) | No |
| Rover shall measure radiation levels | Basic Geiger counter or radiation sensor detecting presence | Quantitative dose rate (µSv/h) with alerts above threshold | Radiation Sensing | No |
| Rover shall provide navigation/orientation data | Basic IMU/compass for heading and tilt | 6/9-DOF IMU with odometry integration for dead-reckoning position tracking | Navigation | No (full dead-reckoning is stretch) |
| Rover shall capture and stream imaging data | Static image capture on demand, transmitted to base station | Real-time low-latency video feed (≥10 fps) from forward-facing camera | Imaging, Operator Feedback | Yes (real-time video) |
| Two-way wireless communication shall enable remote control and telemetry | Reliable command transmission and basic sensor data return within 15 m range | <300 ms latency, simultaneous control + multi-sensor/video streaming within 30 m | Remote Teleoperation, Feedback | No |
| Base station HMI shall display real-time sensor data and vehicle status | Basic text/numeric display of all sensor values and battery/status | Graphical dashboard with graphs, camera view, alerts, and data logging | Operator Feedback, HMI | No |
| Rover chassis and major structural components shall be 3D printed | Primary structure printable and assembled with purchased parts | Optimized lightweight design, durable filament (e.g., PETG/ABS), survives repeated drops/bumps | Construction (3D Printed) | No |
| Power system shall support extended operation | ≥30 minutes continuous use (driving + all sensors active) | ≥90 minutes, low-power modes, real-time battery monitoring and low-battery alerts | System Constraint (Power) | No |
| System shall include emergency stop and fail-safe behaviors | Software/commanded stop of all motors on signal loss or e-stop | Automatic safe state on communication loss (stop + status broadcast) | Safety, Durability | No |

# Requirement Assignment to Team Members

| Requirement Description | Primary Assignee (Functional Area) |
|------------------------|----------------------------------|
| Rover shall provide 4-wheel drive mobility... | Sensor and Actuator Control |
| Rover shall implement steering control... | Sensor and Actuator Control |
| Rover shall detect obstacles/hazards... | Sensor and Actuator Control |
| Rover shall measure atmospheric pressure... | Sensor and Actuator Control |
| Rover shall measure temperature and humidity... | Sensor and Actuator Control |
| Rover shall measure radiation levels... | Sensor and Actuator Control |
| Rover shall provide navigation/orientation data... | Sensor and Actuator Control |
| Rover shall capture and stream imaging data... | Sensor and Actuator Control |
| Two-way wireless communication... | Internet-based Two-way Wireless Communication |
| Base station HMI shall display real-time sensor data... | Human-Machine Interface |
| Rover chassis and major structural components... | System Integration and Safety |
| Power system shall support extended operation... | System Integration and Safety |
| System shall include emergency stop and fail-safe behaviors... | System Integration and Safety |
