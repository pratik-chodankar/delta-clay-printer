# Delta Clay Printing Machine — Patent No. 409171-001

**BTech Mechanical Engineering Capstone Project | 2020-2023**
**Patent Granted: May 2024**

---

## What This Project Is

A complete 3-axis mechatronic system designed, fabricated, and commissioned from scratch. The machine uses delta (parallel) kinematics to position a pneumatic clay extrusion nozzle in 3D space, enabling automated clay sculpting and printing.

Delivered at **Rs. 50,000** against a commercial equivalent cost of **Rs. 250,000** — over 75% cost reduction.

**Patent No. 409171-001** granted May 2024 for the Automated Clay Sculpting Printer design.

---

## System Overview

### Mechanical Design
- 3-axis delta kinematics with 6-link parallel mechanism (2 links per axis)
- Structural frame: wooden ply base and top plates with steel rod vertical guides
- Custom 3D-printed connectors for the delta arm joints
- Pneumatic clay dispensing circuit operating at 2.5 to 3 bar

### Electronics and Control
- **Microcontroller:** Arduino Mega 2560
- **Motion control board:** RAMPS 1.4
- **Stepper motors:** 3x NEMA 17 (4.2 kg-cm torque, 1.8 degrees per step)
- **Stepper drivers:** A4988 microstepping drivers
- **Power supply:** 12V 20A SMPS
- **Pneumatic valve:** Solenoid-actuated for clay extrusion control

### Firmware
- Delta kinematics solver (forward and inverse)
- Stepper motor sequencing with microstepping
- Pneumatic valve timing control
- End-stop interrupt handling
- G-code style command parsing

---

## Key Specifications

| Parameter | Value |
|---|---|
| Kinematics | 3-axis delta parallel mechanism |
| Links per axis | 2 (6 total) |
| Stepper motor | NEMA 17, 4.2 kg-cm, 1.8 deg/step |
| Driver | A4988 microstepping |
| Controller | Arduino Mega 2560 + RAMPS 1.4 |
| Power supply | 12V 20A SMPS |
| Pneumatic pressure | 2.5 to 3 bar |
| Build cost | Rs. 50,000 |
| Commercial equivalent | Rs. 250,000 |
| Cost saving | Over 75% |

---

## Design and Analysis

### CAD
- Full 3D model designed in SolidWorks
- GD&T tolerancing applied to all precision components
- Manufacturing drawings produced for CNC machining and fabrication

### Structural Analysis
- Hand calculations for frame load distribution, bolt sizing, and deflection
- FEA performed using SolidWorks Simulation for static structural verification
- ANSYS Mechanical APDL used for thermal and modal analysis

### DFM Applied Across
- CNC machining (motion components)
- 3D printing (delta arm connectors)
- Fabrication (frame components)

---

## Repository Contents

```
delta-clay-printer/
├── cad/
│   ├── screenshots/             - SolidWorks model screenshots
│   ├── assembly_views/          - Exploded and section views
│   └── kinematic_diagram.png    - Delta kinematics diagram
├── firmware/
│   ├── delta_kinematics.ino     - Forward and inverse kinematics
│   ├── motion_control.ino       - Stepper sequencing and control
│   └── pneumatic_control.ino   - Valve timing and extrusion control
├── documentation/
│   ├── BOM.csv                  - Full bill of materials with costs
│   ├── wiring_diagram.png       - Electrical wiring schematic
│   └── assembly_guide.md        - Step by step assembly instructions
├── analysis/
│   ├── structural_calculations.pdf  - Hand calculations
│   └── fea_results.png              - SolidWorks Simulation results
└── README.md
```

---

## How to Run the Firmware

### Requirements
- Arduino IDE 2.0 or later
- Arduino Mega 2560 board
- RAMPS 1.4 shield
- Marlin firmware base (optional — firmware here is custom)

### Upload
1. Open `delta_kinematics.ino` in Arduino IDE
2. Select board: Tools → Board → Arduino Mega 2560
3. Select port: Tools → Port → (your COM/tty port)
4. Click Upload

### Serial Commands
Connect at 115200 baud. Send commands via Serial Monitor:
```
G1 X10 Y0 Z50    - Move to position X=10, Y=0, Z=50mm
M3               - Activate pneumatic valve (extrude clay)
M5               - Deactivate pneumatic valve
G28              - Home all axes
```

---

## Build Photos

Photos of the physical machine are included in the `cad/` folder.

---

## Patent

**Patent No. 409171-001** — Automated Clay Sculpting Printer
Granted: May 2024
Inventor: Pratik Chodankar

---

## Related

- [swarm-robotics-kilobot](https://github.com/33hacker33/swarm-robotics-kilobot) — MSc dissertation
- [epuck2-autonomous-behaviours](https://github.com/33hacker33/epuck2-autonomous-behaviours) — autonomous robot
- LinkedIn: [pratik-chodankar200114](https://www.linkedin.com/in/pratik-chodankar200114)
