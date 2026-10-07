```markdown
# IoT-Based Smart Parking Management System

An IoT-based smart parking management system implemented and simulated using **Cisco Packet Tracer**.

The system detects vehicle occupancy in parking slots, indicates slot availability, maintains the number of available spaces, and controls parking entry based on slot availability.

---

## Project Objective

The objective of this project is to develop a simulated IoT-based parking system that can:

- Detect vehicles in individual parking slots.
- Determine whether a parking slot is available or occupied.
- Indicate slot status using LEDs.
- Display the number of available parking spaces.
- Control parking entry based on available slots.
- Demonstrate communication between IoT devices through a network.

---

## System Overview

The system consists of multiple parking slots equipped with sensors.

When a vehicle occupies a slot:

```text
Vehicle detected
      ↓
Sensor detects vehicle
      ↓
Controller updates slot status
      ↓
Slot marked OCCUPIED
      ↓
LED changes status
      ↓
Available slot count decreases
```

When the vehicle leaves:

```text
Vehicle leaves
      ↓
Sensor detects empty slot
      ↓
Controller updates slot status
      ↓
Slot marked AVAILABLE
      ↓
LED changes status
      ↓
Available slot count increases
```

The system can also determine whether new vehicles should be allowed to enter the parking area.

```text
Available slots > 0
        ↓
   Entry allowed

Available slots = 0
        ↓
   Parking FULL
        ↓
   Entry restricted
```

---

## Main Components

The project uses Cisco Packet Tracer IoT components such as:

- IoT sensors / proximity sensors
- IoT controller
- LEDs
- Display
- Entry gate / actuator
- IoT gateway
- IoT server
- Network devices

The exact device configuration is contained within the Packet Tracer project file.

---

## System Architecture

```text
                     ┌──────────────┐
                     │  IoT Server  │
                     └──────┬───────┘
                            │
                     ┌──────▼──────┐
                     │ IoT Gateway │
                     └──────┬──────┘
                            │
                   ┌────────▼────────┐
                   │   Controller    │
                   └────────┬────────┘
                            │
          ┌─────────────────┼─────────────────┐
          │                 │                 │
      ┌───▼───┐         ┌───▼───┐         ┌───▼───┐
      │Sensor │         │Sensor │         │Sensor │
      │Slot 1 │         │Slot 2 │         │Slot 3 │
      └───┬───┘         └───┬───┘         └───┬───┘
          │                 │                 │
        ┌─▼─┐             ┌─▼─┐             ┌─▼─┐
        │LED│             │LED│             │LED│
        └───┘             └───┘             └───┘
                            │
                      ┌─────▼─────┐
                      │  Display  │
                      └─────┬─────┘
                            │
                      ┌─────▼─────┐
                      │ Entry Gate│
                      └───────────┘
```

---

## Simulation

The complete working implementation is provided as a Cisco Packet Tracer file:

```text
packet-tracer/smart_parking.pkt
```

Open the `.pkt` file using **Cisco Packet Tracer** to view, configure, and run the simulation.

---

## Expected Behaviour

| Scenario | Expected Behaviour |
|---|---|
| All slots empty | All slots shown as available |
| Vehicle enters Slot 1 | Slot 1 becomes occupied |
| Vehicle enters another slot | Available count decreases |
| Vehicle leaves | Slot becomes available |
| All slots occupied | System indicates parking full |
| Entry attempted when full | Entry is restricted |
| Slot becomes available | Entry can be permitted again |

---

## Team Members and Division of Work

### 1. Vaishnav Sunil Nair
**Role:** Network and System Integration

- Design the overall Packet Tracer topology
- Configure routers, switches, and network connectivity
- Configure IoT gateway/network communication
- Integrate the individual system components

### 2. Kiran S Nair
**Role:** Parking Slot Detection

- Configure parking-slot sensors
- Implement vehicle detection
- Configure individual slot occupancy states
- Test sensor behaviour for occupied and available slots

### 3. Shreyas Nair
**Role:** Control and Actuation

- Configure LEDs for slot status
- Configure parking availability display
- Implement entry-gate control
- Configure actuator behaviour based on parking availability

### 4. Adithyadev B
**Role:** IoT Server and Testing

- Configure the IoT server
- Connect and monitor IoT devices
- Test communication between system components
- Perform complete system testing and identify integration issues

### Shared Responsibilities

All team members will participate in:

- System integration
- Debugging
- Final testing
- Presentation preparation
- Project demonstration

---

## Repository Structure

```text
smart-parking-system/
│
├── README.md
├── .gitignore
│
├── packet-tracer/
│   └── smart_parking.pkt
│
└── assets/
    ├── topology/
    └── screenshots/
```

### packet-tracer/

Contains the main Cisco Packet Tracer simulation.

### assets/topology/

Contains topology or architecture images used for the project.

### assets/screenshots/

Contains screenshots demonstrating the working system.

---

## Technology

**Platform:** Cisco Packet Tracer

**Domain:** Internet of Things (IoT)

**Application:** Smart Parking Management

---

## Project Status

**Status:** In Development

- [ ] Design parking topology
- [ ] Configure IoT devices
- [ ] Configure parking-slot sensors
- [ ] Implement slot status detection
- [ ] Configure LED indicators
- [ ] Configure display
- [ ] Implement entry-gate control
- [ ] Configure IoT server
- [ ] Integrate complete system
- [ ] Test complete simulation
- [ ] Finalize Packet Tracer project
```