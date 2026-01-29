# Overview and Rationale

Through team discussions, we have refined our rover design to focus on **modular exploration of a simulated Martian environment**. The rover is **remotely operated** and collects scientific and environmental data through a variety of sensors, including:

- Atmospheric pressure  
- Temperature and humidity (weather-related)  
- Hazard/obstacle detection  
- Imaging (camera)  
- Navigation/orientation sensors (IMU, odometry)

The rover features **2-wheel drive (2WD) with steering**, with 4-wheel drive (4WD) considered as a possible future enhancement. Most structural components (chassis, mounts, body) will be 3D printed for rapid prototyping and customization. Non-printable components, such as wheels, motors, electronics, and sensors, will be purchased off-the-shelf.

The rover operates over a daisy-chain UART network using an 8-wire ribbon cable to connect all **modular subsystem boards**. Each subsystem is implemented as an independent PCB that safely passes messages while responding only to commands addressed to it.

Remote operation is achieved through bidirectional wireless communication, allowing real-time telemetry, video streaming, and manual control from a base station. In addition, the rover includes a local Human–Machine Interface (HMI) consisting of pushbuttons and a small OLED display, providing immediate system feedback without requiring a remote connection.

This approach emphasizes:

- **Open-ended exploration:** Real-time scientific data collection rather than fixed mission tasks  
- **Subsystem modularity:** Individually designed sensor, actuator, HMI, and communication boards  
- **Reliable integration:** Daisy-chain UART network ensures safe message passing between subsystems  
- **User interaction:** Local OLED display enables real-time monitoring and parameter adjustment  
- **Safety and durability:** Emergency stop, fail-safes, and low-power operation mirror real planetary rover practices  

## Key Feature-to-Requirement Mappings

| Feature | Requirement |
|-------|-------------|
| Mobility | 2WD with steering required for controllable movement across simulated Martian terrain; 4WD may be added as a stretch feature. |
| Scientific exploration | Sensors for pressure, temperature/humidity, and navigation provide environmental data collection. |
| Hazard avoidance | Obstacle detection protects the rover during remote operation when direct visual cues are limited. |
| Imaging and feedback | Camera and real-time telemetry provide operator situational awareness. |
| Local user interface | OLED display and pushbuttons allow on-rover status viewing and parameter adjustment. |
| Remote teleoperation | Wireless link enables driving commands and streams sensor/video data to the base station. |
| Modular subsystem integration | All boards communicate via a UART daisy-chain configuration for reliability and expansion. |

## Requirements Table

| Description | Minimum (Acceptance – Not Complete Failure) | Target | Feature Satisfied | Stretch? |
|------------|---------------------------------------------|--------|-------------------|----------|
| Rover shall provide drive mobility with independent motor control | Forward and backward motion on flat surfaces at ≥0.1 m/s | **2WD** with variable speed control (0.1–0.5 m/s); **4WD supported as an optional enhancement** | Mobility (Drive) | Yes (4WD) |
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

## Requirement Assignment to Team Members

| Team Member | Name | Main Board Functions (Key Responsibilities) | Primary Assignee (Subsystem) |
|------------|------|--------------------------------------------|------------------------------|
| Member 1 | Liam Mabbutt | Rover drive mobility using **2WD baseline** (4WD supported as stretch), motor speed control, steering control, motor feedback, and safety interlocks | Mobility & Motor Control Board |
| Member 2 | Myles White | Obstacle and hazard detection using distance sensors, collision warnings, autonomous slow/stop requests, and safety alerts | Obstacle Detection & Safety Board |
| Member 3 | Isaiah Lacombe | Environmental sensing including atmospheric pressure, temperature, and humidity measurement, calibration, and real-time telemetry | Environmental Sensor Board |
| Member 4 | Ragul Raj RG | Navigation and orientation sensing using IMU and optional wheel odometry, heading estimation, tilt detection, and motion data reporting | Navigation & Orientation Board |
| Member 5 | Arianna Lazaritt | Imaging system control including camera operation, image/video capture, data packetization, and status reporting | Imaging Board |
| Member 6 | Damian Novgorodov | Two-way wireless communication (WiFi/MQTT), command routing between base station and rover subsystems, telemetry aggregation, and system messaging | Wireless Communication Board |
| Member 7 | Christo Jomon Joseph | Local human–machine interface including **OLED display**, pushbuttons, rover status display, user input handling, power monitoring, emergency stop, and fail-safe control | HMI & System Safety Board |

**Alignment Notes**

- The **OLED display satisfies the required HMI subsystem** using a small screen and pushbuttons.
- The HMI board communicates over UART and can:
  - Display live sensor values
  - Show rover status and alerts
  - Adjust setpoints and parameters
- All subsystems remain **modular, independent, and UART-compliant**.

