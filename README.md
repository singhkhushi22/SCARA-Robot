# SCARA Robot Technical Documentation

## 1. Introduction

The SCARA (Selective Compliance Assembly Robot Arm) robot is an industry-standard manipulator known for high speed and precision—ideal for pick-and-place, assembly, and small parts handling. This document details the entire setup, operation, control logic, user interface, and advanced features.

---

## 2. System Overview

- **Degrees of Freedom (DOF):** 4 (Base rotation, shoulder rotation, elbow rotation, vertical Z translation)
- **Manufacturer:** Betrun Robot (Hunan Betrun Robot Co., Ltd.)
- **Teach pendant:** Industrial handheld device with E-Stop, mode select, jog controls, and color touchscreen
- **Controller:** Supports direct teach, program editing, alarms, and Modbus communication

---

## 3. Physical Setup

- **Robot mounting:** Rigidity, electrical safety, and workspace clearance must be ensured
- **Control cabinet:** Houses power supplies, communication interfaces, field wiring
- **Wiring:** Labeled, terminated with cable management for maintainability. I/O includes emergency-stop, sensors, actuators

---

## 4. Teach Pendant User Interface

### 4.1 Startup/Main Screen

- Displays current project name, logged in user, robot mode (AUTO/TEACH/STOP)
- Direct navigation to major functions: Edit/Run, Teaching Points, Jog, I/O Monitor, Settings, Alarms

### 4.2 Edit/Run Program

- Sequence creation: MovP (point), MovL (linear), delay, I/O, conditional logic
- Code block structure, step-by-step visual feedback after execution
- Safety checks during program download

### 4.3 Teach Points

- Jog robot via axis keys/mode
- Save pose to list with tool frame, work frame, and joint coordinate info
- Program displays precise X, Y, Z, θ and mapping to user/task frames

### 4.4 Jog Mode

- Continuous motion or incremental step
- Coordinate mode selection: World, Work, Tool, Joint frames
- Live position feedback, limit/safety alarms if out-of-range

### 4.5 I/O Monitoring

- Real-time digital/analog signal status: sensor/actuator feedback, process triggers
- Quick diagnostics for hardware issues

### 4.6 Alarms & System Info

- Real-time error logs: motion, program, communication faults
- Reset and acknowledgment workflow
- Firmware version, system health check, maintenance reminders

### 4.7 User Permissions/Login

- Role-based access; restrict program change, teach/jog, or settings
- Login, logout: only authorized users can modify/teach
- Audit history and user change log

---

## 5. Modbus Communication and Integration

### 5.1 Protocol Overview

- Slave Address (Station ID) setup
- RTU (RS-232/485) and TCP/IP (Ethernet RJ45) communication supported
- Registers organized in SRAM (persistent) and DRAM (volatile) memory; data mapped as float/int/bool

### 5.2 Master-Slave Operation

- External master (PC, PLC) issues read/write commands to robot controller
- Common operations: program start, status poll, error monitoring, I/O
- Registers mapped to robot states, alarms, user variables

### 5.3 Typical Workflow

1. Master writes “Start” register to begin robot program
2. Robot executes sequence, updates “Done” and “AlarmCode” status registers
3. Master reads status, I/O registers periodically for monitoring
4. Safety/Limit events reflected in register values for external safety circuits

### 5.4 Troubleshooting & Best Practices

- Address conflicts, register mapping errors, baud rate mismatches
- Confirm register data types (float, int, bool)
- Regular error log reviews and audits
- Secure communication for TCP/IP; use VLAN/firewall as needed for networks

---

## 6. Safety

- Emergency stop circuit: Validated on pendant & controller
- Hardware interlocks; software checks for overtravel, load, abnormal scenarios
- Operator safety guidelines for manual jog and program execution

---

## 7. Summary

This technical documentation covers:
- Mechanism setup, wiring, and industrial best practices
- Teach pendant workflows for manual operation and programming
- Real-time I/O and status monitoring
- Robust Modbus RTU/TCP integration for automation and remote control
- Safety and troubleshooting protocols for reliable operation








