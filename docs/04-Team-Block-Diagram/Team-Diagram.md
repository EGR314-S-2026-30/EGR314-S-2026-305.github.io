---
title: Block Diagram, Protocol, and Message Structure
---

## 1️⃣ Team Block Diagram Overview

![Subsystem](block_diagram.png)

sequenceDiagram
    autonumber

    participant WebUser
    participant InPersonUser
    participant HMI as Christo (HMI & Safety)
    participant Wireless as Damian (Wireless Comm)
    participant Motor as Liam (Mobility Board)
    participant Obstacle as Myles (Obstacle Board)
    participant Env as Isaiah (Environmental Board)
    participant Nav as Ragul (Navigation Board)
    participant Camera as Arianna (Imaging Board)

    %% =========================
    %% SYSTEM STARTUP SEQUENCE
    %% =========================
    InPersonUser->>HMI: Power ON Rover
    HMI->>Wireless: System Boot Message
    Wireless->>Motor: Boot Notification
    Wireless->>Env: Boot Notification
    Wireless->>Nav: Boot Notification
    Wireless->>Obstacle: Boot Notification
    Wireless->>Camera: Boot Notification

    Motor-->>Wireless: Status OK
    Env-->>Wireless: Status OK
    Nav-->>Wireless: Status OK
    Obstacle-->>Wireless: Status OK
    Camera-->>Wireless: Status OK

    Wireless->>HMI: All Systems OK
    HMI->>InPersonUser: Display "Rover Ready"

    %% =========================
    %% RECURRING TELEMETRY LOOP
    %% =========================
    loop Every 1 second (Recurring Telemetry)
        Env->>Wireless: Temperature / Humidity / Pressure
        Nav->>Wireless: IMU / Heading Data
        Obstacle->>Wireless: Distance Data
        Motor->>Wireless: Speed Feedback
        Wireless->>HMI: Aggregated Telemetry
        Wireless->>WebUser: Telemetry Update
    end

    %% =========================
    %% WEB USER COMMAND (MOVE)
    %% =========================
    WebUser->>Wireless: Set Speed = 200
    Wireless->>Motor: Motor Command (Set Speed 200)
    Motor-->>Wireless: Speed Acknowledged
    Wireless->>WebUser: Command Confirmed

    %% =========================
    %% OBSTACLE EVENT (EVENT-DRIVEN)
    %% =========================
    Obstacle->>Wireless: Hazard Detected (Distance < Threshold)
    Wireless->>Motor: Emergency Slow/Stop
    Motor-->>Wireless: Speed = 0
    Wireless->>HMI: Display "Obstacle Detected"
    Wireless->>WebUser: Safety Alert

    %% =========================
    %% IMAGE CAPTURE REQUEST
    %% =========================
    WebUser->>Wireless: Capture Image
    Wireless->>Camera: Capture Command
    Camera-->>Wireless: Image Data Packet
    Wireless->>WebUser: Forward Image
    Wireless->>HMI: Image Capture Status

    %% =========================
    %% CALIBRATION EVENT
    %% =========================
    InPersonUser->>HMI: Calibrate Environmental Sensor
    HMI->>Wireless: Calibration Request
    Wireless->>Env: Calibration Command
    Env-->>Wireless: Calibration Complete
    Wireless->>HMI: Display Calibration OK

    %% =========================
    %% MESSAGE DISPOSAL EXAMPLE
    %% =========================
    Env->>Wireless: Temperature Data
    Wireless->>Motor: Forwarded Temperature
    Motor-->>Wireless: Message Not Relevant
    Note right of Motor: Message Disposed
