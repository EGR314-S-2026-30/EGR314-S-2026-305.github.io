[Uploading 314 Team 305 Block Diagram (1)…]()
---
title: Block Diagram, Protocol, and Message Structure
---

## Part 1: Team Block Diagram Overview

<img width="3557" height="1945" alt="314 Team 305 Block Diagram" src="https://github.com/user-attachments/assets/579e0b3f-c2d1-482f-935f-5d62dbccee10" />

Our team’s block diagram was designed using a modular subsystem architecture where each major function (motor control, environmental sensing, navigation, obstacle detection, imaging, wireless communication, and human-machine interface) is implemented on its own board with a dedicated microcontroller and power regulation. Each subsystem is connected through a daisy-chained UART network, allowing each board to manage its own sensors or actuators while relaying data across the system. This structure meets the project requirements by enabling reliable communication, mobility control, sensor feedback, and system monitoring while allowing the rover to remain modular and easily expandable. The source file can be found [here]

## Part 2: Team Communication
![image2](https://github.com/EGR314-S-2026-30/EGR314-S-2026-305.github.io/blob/main/docs/04-Team-Block-Diagram/314%20Team%20Communication.png?raw=true)

The team communication structure uses standardized UART messages to exchange data between subsystems. Sensor boards send periodic updates, the camera subsystem sends frame data and status messages, and the human-machine interface sends display commands and receives status updates. The data travels through the daisy chained network so each subsystem can read the data it needs and pass the message to the next board. The wireless communication board serves as the gateway between the rover and users, transmitting data and receiving control commands. The source file can be found [here](https://github.com/EGR314-S-2026-30/EGR314-S-2026-305.github.io/releases/download/block_diagram_source_files/Team.Communication.drawio).

## Part 3: Message Type Table
[Uploading 314.Team.305.Block.Diagram.drawio…]()

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

## Message Type 1 – Motor Control State Report

| Payload Byte | Type      | Description |
|--------------|----------|-------------|
| 1–2 | uint16_t | 1 |
| 3–4 | int16_t  | Left Motor Speed (PWM) |
| 5–6 | int16_t  | Right Motor Speed (PWM) |
| 7   | uint8_t  | Left Motor Direction (0=Rev,1=Fwd) |
| 8   | uint8_t  | Right Motor Direction |

## Message Type 2 – Motor Status Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 2 |
| 3–4 | uint16_t | Left Motor Current (mA) |
| 5–6 | uint16_t | Right Motor Current (mA) |
| 7 | uint8_t | Left Motor Status Code |
| 8 | uint8_t | Right Motor Status Code |

## Message Type 3 – Camera Frame Data Packet

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 3 |
| 3–4 | uint16_t | Frame ID |
| 5–6 | uint16_t | Packet Index |
| 7–8 | uint16_t | Total Packets in Frame |
| 9–58 | uint8_t[] | Image Data Chunk (50 bytes) |

## Message Type 4 – Camera Status Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 4 |
| 3 | uint8_t | Camera State (0=Off,1=Idle,2=Capturing) |
| 4–5 | uint16_t | Frame Width |
| 6–7 | uint16_t | Frame Height |
| 8 | uint8_t | Error Code |

## Message Type 5 – Gyroscope Data Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 5 |
| 3–6 | float | Angular Velocity X (rad/s) |
| 7–10 | float | Angular Velocity Y |
| 11–14 | float | Angular Velocity Z |

## Message Type 6 – LCD Display Data Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 6 |
| 3–58 | char[] | Display Text (Null-terminated, max 55 chars) |

## Message Type 7 – LCD Status Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 7 |
| 3 | uint8_t | LCD Power State |
| 4 | uint8_t | Backlight Level |
| 5 | uint8_t | Error Code |

## Message Type 8 – Temperature Sensor Data Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 8 |
| 3–6 | float | Temperature (°C) |

## Message Type 9 – Light Sensor Data Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 9 |
| 3–6 | float | Light Intensity (lux) |

## Message Type 10 – Barometric Pressure Sensor Data Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 10 |
| 3–6 | float | Pressure (Pa) |
| 7–10 | float | Estimated Altitude (m) |

## Message Type 11 – Humidity Sensor Data Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 11 |
| 3–6 | float | Relative Humidity (%) |

## Message Type 12 – Distance Sensor Data Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 12 |
| 3–6 | float | Distance (meters) |

## Message Type 13 – System Status Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 13 |
| 3 | uint8_t | System State |
| 4–7 | uint32_t | Uptime (ms) |
| 8–9 | uint16_t | Battery Voltage (mV) |

## Message Type 14 – System Error Code Report

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 14 |
| 3 | uint8_t | Subsystem ID |
| 4 | uint8_t | Error Code |

## Message Type 15 – Debug Message (String)

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 15 |
| 3–58 | char[] | Debug String (Null-terminated, max 55 chars) |

## Message Type 16 – Heartbeat / Alive Signal

| Payload Byte | Type | Description |
|--------------|------|-------------|
| 1–2 | uint16_t | 16 |
| 3 | uint8_t | System State |
| 4 | uint8_t | Error Flag |

## How the Communication Sequence Satisfies User Needs and Product Requirements

The communication sequence was designed so that every major user need maps directly to one or more message types in the UART daisy-chain network.
Remote situational awareness is satisfied through continuous periodic transmission of Message Types 8–12, which stream temperature, humidity, pressure, light, and distance readings to the wireless board and on to the base station — giving the operator a live picture of the rover's environment without manual requests.
Safe navigation is handled through the relationship between the distance sensor (Type 12) and motor control (Type 1). When an obstacle is detected within threshold, the data propagates through the chain and can trigger an automatic slow or stop, satisfying the hazard avoidance requirement. The HMI board simultaneously updates the OLED display via Type 6 to alert the operator.
Operator control reliability is supported by the two-way structure of the system. Motor commands arrive from the base station as Type 1 packets, and Motor Status Reports (Type 2) flow back confirming execution — giving the operator confidence the rover is responding correctly.
System health is covered by Types 13–16. The System Status Report (Type 13) carries battery voltage and uptime, the Error Code Report (Type 14) lets any subsystem flag a fault, and the Heartbeat (Type 16) lets the base station detect a dropout and trigger a fail-safe — satisfying the safety and power management requirements.
Finally, the local HMI satisfies the need for on-rover feedback independent of the wireless link. Even if the wireless connection is lost, the OLED continues receiving updates through the daisy-chain, ensuring the rover never operates completely without feedback.

## Message Structure Design and Decision-Making Process

The message structure was built around three constraints: limited UART bandwidth, the need for each board to filter only relevant messages, and keeping the system expandable.
Every message begins with a fixed uint16_t type field. Each board reads these first two bytes to decide whether to act on the message or pass it along. A 16-bit field gives room for future expansion without restructuring the protocol. An addressed source-destination scheme was considered but rejected — in a daisy-chain topology where all boards see all traffic, it added complexity without a real benefit.
Payload sizes were kept small intentionally. Most sensor messages carry just a 2-byte type header and a 4-byte float, keeping each message focused on a single data source. This meant boards could be developed and tested independently, which was important with seven team members working on separate boards.
The camera packet (Type 3) was the most complex decision. Streaming video over UART requires chunking frames into 50-byte segments with a Frame ID and Packet Index so the receiver can reassemble them in order. The 50-byte size was chosen to avoid blocking the bus for too long while still making meaningful progress per transmission.
The Heartbeat (Type 16) and Debug message (Type 15) were both added during development rather than planned from the start — the heartbeat to distinguish genuine faults from low-activity periods, and the debug message to let boards broadcast readable strings to the base station during integration testing without needing a separate debugger on each board.

## Top 5 Software Design Changes Since the Software Proposal

1. Broadcast Filtering Replaced Addressed Messaging
The original proposal used source-destination address fields on every message. During integration, maintaining address tables across seven independently developed boards created version-control headaches — a change on one board required updates everywhere. The team switched to a broadcast model where every board sees all traffic and filters by message type only. This simplified firmware across all boards and made adding new subsystems as easy as defining a new message type.
2. Heartbeat Message Added
The proposal had no keep-alive mechanism. During bench testing, the base station had no way to confirm the network was still active during low-activity periods, triggering false disconnection warnings. The team added Message Type 16, a 500ms periodic heartbeat from the HMI board carrying system state and an error flag. The base station now treats absence of this signal as the definitive sign of a failure, eliminating the false warnings entirely.
3. Motor Status Changed from Event-Driven to Continuous
Originally the motor board only transmitted a status message when something changed. This left the base station unable to confirm rover state after a brief dropout or fresh connection. The team changed Message Type 2 to transmit continuously at 10Hz regardless of state changes, ensuring the operator always has an accurate motion picture within 100ms of connecting.
4. Environmental Sensors Split into Individual Message Types
The proposal combined all environmental readings — temperature, humidity, pressure, and light — into one message to reduce bus traffic. In practice, these sensors lived on different boards with different owners and sampling rates, so one board would have had to collect data from the others before transmitting. The team split them into Types 8–11, each sent independently by its own board. This restored full subsystem independence and made each board's firmware simpler to test.
5. Camera Transmission Changed to Chunked Packets
The proposal assumed the camera board would send complete JPEG frames as single large UART messages. Testing showed these large bursts blocked the bus long enough to delay time-sensitive messages like motor commands and obstacle alerts. The team redesigned transmission as 50-byte chunks (Type 3) interleaved with other traffic, with Frame ID and Packet Index fields for reassembly. This kept safety-critical messages flowing without interruption during active video streaming.
