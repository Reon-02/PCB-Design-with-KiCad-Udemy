# Solar Power Supply

## Overview

This project is a solar power supply PCB designed as part of the **PCB Design with KiCad - Updated for KiCad 9** Udemy course.

The circuit is designed to accept power from a solar source and provide a regulated output using a boost converter based on the **AP3015AKTR-G1**.

The design includes input protection, battery connection, power switching, a boost converter, filtering, and output voltage feedback.

---

## Features

- Solar power input
- Battery connection
- Reverse-polarity protection
- Power switching circuit
- AP3015AKTR-G1 boost converter
- Inductor-based DC-DC conversion
- Schottky diode
- Output voltage feedback network
- Input and output filtering
- Custom PCB layout
- Ground plane
- Design Rule Check (DRC)
- Interactive HTML BOM
- Gerber generation and verification
- KiCad 3D visualization

---

## Working Principle

The solar power supply consists of an input section, battery/power switching section, and a boost converter section.

### 1. Solar Input

The solar panel is connected through the solar input connector.

The input passes through **D1 (SS14 Schottky diode)** before reaching the main power rail.

The diode provides protection against reverse current from the rest of the circuit toward the solar source.

```text
Solar Input
     │
     ▼
   SS14
     │
     ▼
 Power Rail
```

### 2. Battery Connection

A battery can be connected through the battery connector.

The battery and solar input are connected to the power switching section, allowing the circuit to operate from the available power source.

---

### 3. Power Switching

The **2N7002 MOSFET** is used in the power switching/control section.

Resistors connected to the MOSFET provide the required gate biasing.

The MOSFET controls the connection between the input power and the boost converter section.

```text
Solar / Battery
       │
       ▼
   Power Switch
       │
       ▼
   Boost Converter
```

---

### 4. Boost Converter

The main voltage conversion is performed by the **AP3015AKTR-G1** boost converter.

The input voltage is supplied to the **VIN** pin of the AP3015.

An external inductor **L1 (10 µH)** is connected to the switching node.

The AP3015 controls the switching operation to transfer energy through the inductor and generate a higher output voltage.

```text
             L1
Input ──────coil─────┐
                     │
                 AP3015
                     │
                     ▼
                Switching
                     │
                    D2
                     │
                     ▼
                  Output
```

---

### 5. Output Rectification and Filtering

**D2 (SS14)** is used as the Schottky diode in the boost converter output path.

The output capacitors provide filtering and reduce voltage ripple.

The resulting voltage is available at the output connector.

---

### 6. Output Voltage Feedback

The output voltage is monitored using the feedback network consisting of:

- **R1 = 1 MΩ**
- **R2 = 604 kΩ**

The voltage divider feeds the output voltage back to the **FB** pin of the AP3015.

The AP3015 adjusts its switching operation according to the feedback voltage to regulate the output.

```text
              Output
                 │
                R1
                 │
                 ├──────► FB
                 │
                R2
                 │
                GND
```

---

## Schematic

The complete Solar Power Supply circuit was designed using KiCad.

![Solar Power Supply Schematic](./Images/Schematic.png)

---

## PCB Design

The PCB was designed using KiCad with the components arranged for a compact solar power supply circuit.

### PCB Layout

![PCB Layout](./Images/PCB_Layout.png)

---

## 3D Visualization

### Front View

![3D Front View](./Images/3D_front.png)

### Back View

![3D Back View](./Images/3D_back.png)

---

## Components

| Reference | Component | Value / Part |
|---|---|---|
| U1 | Boost Converter | AP3015AKTR-G1 |
| Q1 | N-Channel MOSFET | 2N7002 |
| L1 | Inductor | 10 µH, 680 mA |
| D1 | Schottky Diode | SS14 |
| D2 | Schottky Diode | SS14 |
| R1 | Resistor | 1 MΩ |
| R2 | Resistor | 604 kΩ, 1% |
| R3 | Resistor | 10 kΩ |
| R4 | Resistor | 1 MΩ |
| C1 | Capacitor | 4.7 µF, 50 V, X7R |
| C2 | Capacitor | 22 µF, 10 V, X7R |
| C3 | Capacitor | 10 pF, 50 V, X7R |
| J2 | Connector | Battery Input |
| J4 | Connector | Solar Input |
| J3 | Connector | Power Switch |
| J1 | Connector | Output |

---

## Bill of Materials

An Interactive HTML BOM was generated using **InteractiveHtmlBom**.

### Interactive BOM

**[Open Interactive BOM](https://reon-02.github.io/PCB-Design-with-KiCad-Udemy/03_Solar_Power_Supply/BOM/Solar_Power_Supply_ibom.html)**

The Interactive BOM provides:

- Component references
- Component values
- Footprints
- Component quantities
- Component locations
- Datasheet information where available
- Interactive PCB component highlighting

---

## Design Verification

### Design Rule Check

The PCB was checked using KiCad's **Design Rule Checker (DRC)**.

![DRC Results](./Images/DRC.png)

### Gerber Verification

The generated manufacturing files were opened and inspected using KiCad Gerber Viewer.

![Gerber Viewer](./Images/Gerber_viewer.png)

### Gerber Viewer with Ground Zone

![Gerber Viewer with Zone](./Images/Gerber_viewer_zone.png)

---

## Manufacturing Files

The `Gerbers/` directory contains the manufacturing outputs generated from KiCad, including:

- Front copper
- Back copper
- Front solder mask
- Back solder mask
- Front solder paste
- Back solder paste
- Front silkscreen
- Back silkscreen
- Board outline
- PTH drill file
- NPTH drill file
- Gerber job file

---

## Datasheets

Datasheets for the main components used in the design are included in the `Datasheets/` directory.

- [AP3015A Datasheet](./Datasheets/AP3015_A.pdf)
- [Abracon ASPI-0630LR-100M-T15 Datasheet](./Datasheets/ASPI-0630LR-100M-T15_Abracon.pdf)
- [2N7002A Datasheet](./Datasheets/NDS7002A-D.PDF)
- [SS14 Datasheet](./Datasheets/SS14_ON.pdf)

---

## KiCad Project Files

The complete KiCad project files are available in the `KiCad/` directory.

```text
KiCad/
├── solar power supply.kicad_pro
├── solar power supply.kicad_sch
└── solar power supply.kicad_pcb
```

---

## Project Structure

```text
03_Solar_Power_Supply/
│
├── README.md
│
├── KiCad/
│   ├── solar power supply.kicad_pro
│   ├── solar power supply.kicad_sch
│   └── solar power supply.kicad_pcb
│
├── BOM/
│   └── Solar_Power_Supply_ibom.html
│
├── Datasheets/
│   ├── AP3015_A.pdf
│   ├── ASPI-0630LR-100M-T15_Abracon.pdf
│   ├── NDS7002A-D.PDF
│   └── SS14_ON.pdf
│
├── Gerbers/
│   ├── Gerber files
│   └── Drill files
│
└── Images/
    ├── Schematic.png
    ├── PCB_Layout.png
    ├── 3D_front.png
    ├── 3D_back.png
    ├── DRC.png
    ├── Gerber_viewer.png
    └── Gerber_viewer_zone.png
```

---

## What I Practiced

Through this project, I practiced:

- Solar power supply circuit design
- Boost converter circuit design
- AP3015 boost converter
- MOSFET switching
- Schottky diode selection
- Inductor selection
- Feedback voltage divider design
- Schematic capture
- Component selection
- Footprint assignment
- SMD PCB layout
- PCB routing
- Ground plane creation
- Design Rule Checking
- Interactive BOM generation
- Gerber generation
- Gerber verification
- KiCad 3D visualization
- Datasheet reference
- Preparing PCB files for manufacturing

---

## Course

This project was completed as part of:

**[PCB Design with KiCad - Updated for KiCad 9](https://www.udemy.com/share/105YR03@hdEVWNpVydDwXK-DHMVmjIG6j6jP2o1doZVhvYaCLZwN9b4QRBgg-SJO-xgzQPG_Kw==/)**

**Platform:** Udemy
