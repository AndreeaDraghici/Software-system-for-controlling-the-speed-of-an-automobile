# Adaptive Cruise Control System

## Overview
This repository contains the implementation of an **Adaptive Cruise Control System** for automobiles. The system is designed to manage the vehicle's speed autonomously, allowing the driver to have minimal input. It maintains a set cruising speed and adjusts it dynamically based on the proximity of other vehicles, ensuring safety and comfort.

---

## Features
- **Cruising Speed Maintenance**: Maintains the vehicle's speed at a predefined cruising value.
- **Proximity Detection**: Utilizes radar to measure the distance to the nearest vehicle.
- **Dynamic Braking and Acceleration**: Adjusts vehicle speed to ensure a safe distance from other vehicles.
- **Driver Alerts**: Provides warnings in conjunction with braking for enhanced safety.
- **Emergency Stops**: Automatically stops the vehicle if required.

---

## System Inputs
The system takes the following inputs:
1. **Cruising Speed**: Predefined target speed set by the user.
2. **Distance to the Next Vehicle**: Measured using a radar system.
3. **Current Speed**: Real-time speed of the automobile.

---

## System Outputs
The outputs of the system include:
1. **Acceleration Command**: Increases the vehicle's speed to match the cruising speed.
2. **Braking Command**: Reduces the vehicle's speed to maintain a safe distance.
3. **Warning Command**: Alerts the driver during braking operations.
4. **Stopping Command**: Stops the vehicle if the speed reaches zero.

---

## Key Specifications
1. **Startup Behavior**:
   - Upon initialization, the system activates the acceleration command.
   - During operation:
     - If the current speed is less than the cruising speed, the acceleration command is activated.
     - If the current speed exceeds or matches the cruising speed, the braking command is activated.

2. **Proximity Detection**:
   - If another vehicle is detected ahead within the configured safety distance, the system activates the braking command.
   - Braking may continue until the vehicle comes to a complete stop.

3. **Discrete Acceleration and Braking**:
   - Adjustments are made in discrete steps of `k \cdot f`, where:
     - `f` is a constant acceleration/braking value (measured in m/s²).
     - `a` (acceleration/deceleration constant) is configurable during initialization.

4. **Time Interval Updates**:
   - All values are updated in discrete time intervals of `k \cdot Δt`, where:
     - `Δt` is the configurable time interval (e.g., 1 millisecond).

---

## Configuration Parameters
- **Cruising Speed**: Set by the user.
- **Safety Distance**: Adjustable during system initialization.
- **Acceleration/Deceleration Constant (`a`)**: Defined during setup.
- **Time Interval (`Δt`)**: Determines the frequency of updates.

---

## Usage
To use this system:
1. Set the cruising speed.
2. Configure the safety distance, acceleration/deceleration constants, and time interval.
3. Activate the system. It will autonomously adjust the vehicle's speed based on the surrounding traffic.

