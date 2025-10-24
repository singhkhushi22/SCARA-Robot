# SCARA Robot — Technical Documentation

## 1. Introduction

The SCARA (Selective Compliance Assembly Robot Arm) robot is designed for high-performance pick-and-place, assembly, and controlled automation tasks. This documentation details:
- Hardware overview
- Teach pendant user-interface
- Modbus-based communication (PC or PLC to robot)
- Real hardware, UI, and wiring images

---

## 2. Hardware & System Layout

### 2.1 Robot Main View
The physical Betrun SCARA robot in operational setup:
![SCARA Robot Front View](143aa46d-650f-4b69-ae49-d4bd8223f13f.jpg)

### 2.2 Control Panel & Wiring
Neat wiring and control cabinet for safe, reliable connections:
![Wiring Cabinet](372c6f33-e871-4e43-8bc0-6c11f99c6575.jpg)

### 2.3 Detailed Wiring
Labelling and structured wiring for troubleshooting and maintenance:
![Detailed Wiring](d134643f-a2e4-4cdf-bdde-d560cc32f6a2.jpg)

---

## 3. Teach Pendant User Interface

### 3.1 Device Overview
Handheld teach pendant for manual and programmatic control, featuring E-Stop, axis jog, and display:
![Teach Pendant](4871db07-e28e-48a9-968f-edfa44bb8ab1.jpg)

### 3.2 Home Screen
Shows project, user status, current robot mode (AUTO, TEACH), and quick menus.
![Home Screen](cf6e571e-406b-4370-889d-255f232898a5.jpg)

### 3.3 Editing & Running Programs
Motion routines are created, edited, and run from this tab:
![Edit/Run Tab](f41aa063-5320-4f98-98b9-1e2d747a9cc7.jpg)

### 3.4 Teaching Points & Coordinates
Jog the robot, teach/save positions, and review pose data:
![Teaching Points](143aa46d-650f-4b69-ae49-d4bd8223f13f.jpg)

### 3.5 Jog Mode
Manual movement using pendant keys for each robot axis; step, continuous, world, and joint frame options:
![Jog Mode](d8f109a5-daab-49e6-bf05-b24b7e9efd73.jpg)

### 3.6 I/O Monitoring
Live display of digital and analog inputs/outputs for quick testing and troubleshooting:
![I/O Monitor](76fdabb8-11b5-4f48-90c6-f033eed46c25.jpg)

### 3.7 Alarms & System Info
See system errors, firmware version, and take safety actions:
![Alarm Screen](fc32d1cd-27e6-46bb-b264-9f4ef74f7352.jpg)
![System Info](f41aa063-5320-4f98-98b9-1e2d747a9cc7.jpg)

### 3.8 User Login & Permissions
Restrict access, control program editing, and protect the system:
![Login Screen](5fd232c4-8b65-4887-b7b5-d3367537762f.jpg)

---

## 4. Modbus Communication System

### 4.1 System Block Diagram
Overview of PC/PLC master, Modbus RTU/TCP link, and robot controller integration:
![Modbus Block Diagram](7038facc-cf12-41e1-bca1-eca4390ea3c4.jpg)

### 4.2 Pendant UI ↔ Modbus Register Mapping
How user actions update Modbus registers (e.g., program start, jog updates, alarm feedback):
![UI-Modbus Integration](2f1a6116-78ab-4cfb-8311-242043ed3f51.jpg)

#### Modbus Setup Highlights
- Slave address & protocol config (RTU or TCP/IP)
- Register mapping (SRAM, DRAM)
- Match data types for reliability (int, float, bool)
- Typical flow: Write “Start” → robot executes → update status/alarm → master reads/monitors

---

## 5. Project Highlights

- **Direct hands-on programming** with teach pendant (jog, point, run, alarm handling)
- **Industrial wiring and safety** (photos included)
- **Turnkey Modbus integration:** Easy connection with PLC or PC for automation
- **Stepwise UI screens**: All main pendant functions shown
- **Error/status feedback** for robust real-world operation

---




