# 🏭 Automated Warehouse & Crane System

A complete industrial automation project developed using **Siemens TIA Portal, PLC programming, WinCC HMI, and Factory I/O**.

The system simulates an automated warehouse where products are detected, transported by conveyors, lifted, positioned, and stored automatically in a **54-position storage system**.

The project was designed to reproduce a realistic industrial control architecture, combining **PLC sequencing, actuator control, storage management, operator supervision, and industrial simulation**.

---

## 🎥 Project Demonstration

A complete demonstration of the system is provided in the repository, showing the automated sequence, crane operation, storage process, and HMI interaction.
![Warehouse HMI](warhouse%20hmi.png)
---

## 🏗️ System Architecture

```text
                    ┌───────────────┐
                    │     HMI       │
                    │ Control /     │
                    │ Monitoring    │
                    └───────┬───────┘
                            │
                            ▼
                    ┌───────────────┐
                    │  Siemens PLC  │
                    │               │
                    │ State Machine │
                    │ Process Logic │
                    └───────┬───────┘
                            │
                ┌───────────┼───────────┐
                ▼           ▼           ▼
            Conveyors     Lift        Forks
                │           │           │
                └───────────┼───────────┘
                            ▼
                    ┌───────────────┐
                    │ Crane /       │
                    │ Storage       │
                    └───────┬───────┘
                            │
                            ▼
                    ┌───────────────┐
                    │  Factory I/O  │
                    │  Simulation   │
                    └───────────────┘
```

---

## ⚙️ Automated Process

The warehouse operates through a sequential control strategy:

```text
Product Detection
       ↓
Loading
       ↓
Transport
       ↓
Lifting
       ↓
Positioning
       ↓
Storage
       ↓
Return
       ↓
Next Product
```

The PLC coordinates each stage using sensor feedback and process states.

The main sequence is implemented as a **step-based state machine** with dedicated process flags for loading, sorting, and storage.

---

## 🧠 PLC Control

The project uses both **SCL (Structured Control Language)** and **LAD (Ladder Logic)**.

### SCL

The state machine manages the overall process sequence and transitions between operating states.

The storage algorithm also searches the warehouse for an available position and assigns the first available location to the product.

### LAD

Ladder logic is used for machine-level control, including:

* Conveyor operation
* Lift movement
* Fork movement
* Sensor conditions
* Timers
* Actuator sequencing

## The loading and sorting functions directly coordinate conveyor, lift, and fork operations based on sensor feedback.

## 📦 Storage Management

The warehouse contains **54 storage locations**.

Each location is represented by a Boolean state indicating whether the position is occupied. When a product enters the storage sequence, the PLC searches the array for an available position, assigns it, and updates the storage state.
This allows the crane to receive a target position dynamically instead of relying on fixed storage locations.

---

## 🖥️ HMI

A WinCC HMI provides the operator interface for the system.

### Main Functions

* Start / Stop operation
* Load / Unload commands
* Automatic operation
* Manual operation
* Machine-state visualization
* Alarm monitoring
* Operator navigation
* System supervision

The HMI is integrated with the PLC and provides a visual representation of the machine state and operator controls.

---

## 🏗️ Main Automation Components

| Component   | Function                        |
| ----------- | ------------------------------- |
| Siemens PLC | Main control and sequencing     |
| Conveyors   | Product transportation          |
| Lift        | Vertical movement               |
| Forks       | Product transfer                |
| Crane       | Storage positioning             |
| Sensors     | Position and process feedback   |
| HMI         | Operator control and monitoring |
| Factory I/O | Industrial simulation           |

---

## 🛠️ Technologies

* **Siemens TIA Portal**
* **Siemens PLC / PLCSIM**
* **SCL / Structured Text**
* **Ladder Logic (LAD)**
* **WinCC HMI**
* **Factory I/O**
* **Industrial Automation**
* **Sequential Control**
* **State Machines**

---



## 🚀 Engineering Highlights

* Developed a complete PLC-based warehouse automation system
* Implemented a step-based state machine in SCL
* Developed LAD logic for conveyors, lift, and forks
* Implemented dynamic 54-position storage allocation
* Developed a WinCC HMI for operator interaction and monitoring
* Integrated automatic and manual operating modes
* Used sensor feedback and timers for sequential control
* Simulated and tested the complete system in Factory I/O
<video src="./warhouse video.mp4" controls width="800"></warehouse video>
[▶️ Watch the demonstration](./warehouse%20video.mp4)
---

## 👨‍💻 Author

**Mohamed Salah Dahassa**

Automation & Control Engineer

**Areas of interest:** Industrial Automation · PLC · HMI/SCADA · Robotics · Control Systems · Industrial Communication
