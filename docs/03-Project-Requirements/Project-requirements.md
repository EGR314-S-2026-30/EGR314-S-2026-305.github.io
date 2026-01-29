# Project Overview

Through team discussions, we designed our rover to explore a simulated Martian environment. The rover is remotely operated and collects scientific and environmental data through a variety of sensors, including atmospheric pressure, temperature and humidity, hazard detection, imaging, and navigation/orientation sensors like IMU and odometry. To move across the terrain, the rover features 2-wheel drive with steering, with 4-wheel drive considered as a future enhancement. Most structural components, including the chassis, mounts, and body, are 3D printed for rapid prototyping and customization, while wheels, motors, electronics, and sensors are purchased from suppliers.

All subsystems communicate through a daisy-chained UART network, allowing independent boards to send and receive messages safely. Remote operation is achieved through bidirectional wireless communication for real-time telemetry, video streaming, and manual control. A local Human–Machine Interface consisting of pushbuttons, levers, and an OLED display, provides immediate system feedback without needing a remote connection.

# Project Rationel

Our team designed this as an open-ended exploration platform focused on collecting real-time scientific data rather than following fixed tasks. It uses a modular setup with separate sensor, actuator, HMI, and communication boards, all connected through a daisy-chained UART network for reliable communication between subsystems. A local OLED display allows users to monitor data and adjust settings in real time, while safety features like an emergency stop, built-in fail-safes, and low-power operation are included to relate to real planetary rover designs.

## Key Feature-to-Requirement Mappings

Our rover is designed as an open-ended exploration platform, focused on collecting scientific data rather than performing fixed tasks. Each feature of the rover naturally leads to a set of requirements that ensure the system works as intended:

- **Mobility:** To explore the terrain effectively, the rover needs drive and steering capabilities. This translates to a requirement for 2WD with steering, and a stretch goal for 4WD.
- **Scientific Exploration:** To collect environmental data, the rover requires sensors for pressure, temperature, humidity, and navigation, all with calibrated outputs for real-time telemetry.
- **Hazard Avoidance:** Since the rover operates remotely, obstacle detection is required to prevent collisions. This includes alerts and, in advanced operation, automatic slow or stop behaviors.
- **Imaging and Feedback:** Cameras and video streaming provide situational awareness to the operator, which is critical for safe navigation and mission planning.
- **User Interaction:** A local OLED display and input buttons allow on-rover monitoring and control, providing redundancy if wireless control is lost.
- **Modular Subsystem Integration:** All subsystems need to communicate reliably via UART to ensure messages reach the correct module, allowing future expansion without reworking the network.
- **Safety and Power Management:** Emergency stops, fail-safes, and low-power operation are required to ensure both operator safety and system longevity.

## Requirements Table

| Description | Minimum (Acceptance – Not Complete Failure) | Target | Feature Satisfied | Stretch? |
|------------|---------------------------------------------|--------|-------------------|----------|
| Rover shall provide drive mobility with independent motor control | Forward and backward motion on flat surfaces at ≥0.1 m/s | 2WD with variable speed control (0.1–0.5 m/s); 4WD supported as an optional enhancement | Mobility (Drive) | Yes (4WD) |
| Rover shall implement steering control for directional navigation | Basic turning using differential drive or simple steering mechanism | Controlled steering with ≥30° effective turning radius | Mobility (Steering) | No |
| Rover shall detect obstacles or hazards and alert or autonomously slow/stop | Detect obstacles ≤0.5 m ahead and alert operator | Detection ≤1.5 m with proportional speed reduction or automatic stop | Hazard Avoidance, Safety | No |
| Rover shall measure atmospheric pressure | Functional barometric sensor reporting pressure values | Calibrated sensor (0–1100 hPa) with real-time data streaming to base station | Environmental Sensing (Pressure) | No |
| Rover shall measure temperature and humidity | Basic temperature (±2 °C) and relative humidity sensing | High-accuracy sensing (±0.5 °C, ±3% RH) with continuous telemetry | Environmental Sensing (Weather) | No |
| Rover shall provide navigation and orientation data | Basic IMU providing heading and tilt information | 6- or 9-DOF IMU with optional wheel odometry integration | Navigation & Orientation | No |
| Rover shall capture and transmit imaging data | Static image capture on operator request | Real-time video streaming at ≥10 fps | Imaging & Operator Feedback | Yes |
| Two-way wireless communication shall enable remote control and telemetry | Reliable command transmission and sensor data return within 15 m | <300 ms latency with simultaneous control, telemetry, and imaging | Teleoperation & Wireless Communication | No |
| Rover shall provide a local human–machine interface | OLED displays basic system status and sensor data | Menu-driven OLED interface with alerts, parameters, and live data | Human–Machine Interface (OLED) | No |
| Rover chassis and major structural components shall be 3D printed | Primary structure printable and assembled with purchased components | Lightweight and durable design suitable for repeated testing | Mechanical Construction | No |
| Power system shall support extended operation | ≥30 minutes of continuous operation with all subsystems active | ≥90 minutes with battery monitoring and low-power modes | Power Management | No |
| System shall include emergency stop and fail-safe behaviors | Software-commanded stop on signal loss or emergency input | Automatic safe state with system-wide status broadcast | System Safety | No |
| Communication network shall reliably support all subsystem messaging | Messages may be delayed or lost <5% of the time | <1% message loss, ≤50 ms latency | Modular Subsystem Integration | No |
| Rover shall not exceed weight limit of chassis | Total weight ≤5 kg | ≤4.5 kg for optimal mobility and motor efficiency | Mechanical Construction & Mobility | No |
| Maximum current draw per subsystem | Each subsystem <2 A under normal operation | Each subsystem <1.5 A with power monitoring | Power Management & Safety | No |
| Environmental tolerance for sensors and electronics | Functional at 0–40°C, 20–80% RH | Functional at -10–50°C, 10–90% RH | Environmental Sensing & System Safety | No |

## Requirement Assignment to Team Members

| Team Member | Name | Main Board Functions (Key Responsibilities) | Primary Assignee (Subsystem) |
|------------|------|--------------------------------------------|------------------------------|
| Member 1 | Liam Mabbutt | Rover drive mobility using 2WD baseline (4WD supported as stretch), motor speed control, steering control, motor feedback, and safety interlocks | Mobility & Motor Control Board |
| Member 2 | Myles White | Obstacle and hazard detection using distance sensors, collision warnings, autonomous slow/stop requests, and safety alerts | Obstacle Detection & Safety Board |
| Member 3 | Isaiah Lacombe | Environmental sensing including atmospheric pressure, temperature, and humidity measurement, calibration, and real-time telemetry | Environmental Sensor Board |
| Member 4 | Ragul Raj RG | Navigation and orientation sensing using IMU and optional wheel odometry, heading estimation, tilt detection, and motion data reporting | Navigation & Orientation Board |
| Member 5 | Arianna Lazaritt | Imaging system control including camera operation, image/video capture, data packetization, and status reporting | Imaging Board |
| Member 6 | Damian Novgorodov | Two-way wireless communication (WiFi/MQTT), command routing between base station and rover subsystems, telemetry aggregation, and system messaging | Wireless Communication Board |
| Member 7 | Christo Jomon Joseph | Local human–machine interface including OLED display, pushbuttons, rover status display, user input handling, power monitoring, emergency stop, and fail-safe control | HMI & System Safety Board |

