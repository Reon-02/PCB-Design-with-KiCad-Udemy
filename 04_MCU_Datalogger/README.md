# MCU Data Logger

## Overview

This project is an **MCU Data Logger PCB** designed as part of the **PCB Design with KiCad - Updated for KiCad 9** Udemy course.

The project is developed around an **ATmega328P-AU microcontroller** and includes a real-time clock, EEPROM memory, programming interface, serial interface, and exposed I/O connections. Both **2-layer and 4-layer PCB versions** are included to document the different PCB implementations.

---

## Features

- ATmega328P-AU microcontroller
- DS1337S real-time clock
- External EEPROM memory
- I²C communication
- UART serial interface
- ISP programming interface
- Exposed digital I/O
- External connectors for power and communication
- Crystal oscillator for the MCU
- RTC crystal
- Reset circuitry
- Power indication LED
- Decoupling capacitors
- 2-layer PCB version
- 4-layer PCB version
- Design Rule Check (DRC)
- Interactive HTML BOM
- Gerber generation and verification
- KiCad 3D visualization

---

## Working

The MCU Data Logger uses the **ATmega328P-AU** as the main controller. The microcontroller communicates with the **DS1337S real-time clock** and external EEPROM devices through the **I²C bus**.

The DS1337S provides timekeeping information to the microcontroller, allowing logged information to be associated with the corresponding time. The EEPROM provides non-volatile memory for storing data even when the main power is removed.

The ATmega328P-AU can also communicate with external equipment through the **UART interface**, with dedicated TX and RX connections available on the connector section.

For programming and firmware development, an **ISP interface** is provided with MISO, MOSI, SCK, RESET, VCC, and GND connections. Additional digital I/O pins are also exposed through connectors for interfacing with external circuits.

The MCU uses an external crystal oscillator for its clock, while the DS1337S uses a dedicated **32.768 kHz crystal** for real-time clock operation. Reset circuitry, power indication, and decoupling components are included to support reliable operation of the board.

---

## Schematic

The complete MCU Data Logger circuit was designed using KiCad.

![MCU Data Logger Schematic](./Images/Schematic.png)

---

## PCB Design

Two PCB implementations were developed for this project:

### 2-Layer PCB

The 2-layer version demonstrates the PCB layout using two copper layers for routing the circuit.

### 4-Layer PCB

The 4-layer version demonstrates a multilayer PCB implementation with additional copper layers for routing and board design.

Both versions are included in the project to document the different PCB layer configurations.

---

## 3D Visualization

The project includes KiCad 3D visualizations of the PCB design.

![3D Front View](./Images/3D_front.png)

![3D Back View](./Images/3D_back.png)

---

## Main Components

| Reference | Component | Description |
|---|---|---|
| U1 | ATmega328P-AU | Main microcontroller |
| U2 | DS1337S | Real-time clock |
| U3, U4 | EEPROM | Non-volatile data storage |
| Y1 | Crystal | MCU clock source |
| Y2 | 32.768 kHz Crystal | RTC clock source |
| J1 | Connector | I²C / power connections |
| J2 | Connector | UART serial interface |
| J3 | GPIO Connector | Digital I/O |
| J4 | ISP Connector | MCU programming interface |

---

## Bill of Materials

An Interactive HTML BOM was generated using **InteractiveHtmlBom**.

### Interactive BOM

**[Open Interactive BOM](https://reon-02.github.io/PCB-Design-with-KiCad-Udemy/04_MCU_Datalogger/BOM/MCU_Datalogger_ibom.html)**

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

The PCB designs were checked using KiCad's **Design Rule Checker (DRC)**.

![DRC Results](./Images/DRC.png)

### Gerber Verification

The generated manufacturing files were opened and inspected using KiCad Gerber Viewer.

![Gerber Viewer](./Images/Gerber_viewer.png)

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
- Drill files
- Gerber job file

---

## Datasheets

Datasheets for the main components used in the design are included in the `Datasheets/` directory.

- [21941 Datasheet](./Datasheets/21941.pdf)
- [ATmega328P-AU Datasheet](./Datasheets/ATMEGA328PAU_Microchip_Technology.pdf)
- [DS1337S Datasheet](./Datasheets/DS1337S_Maxim_Integrated_Products.pdf)

---

## KiCad Project Files

The project contains separate KiCad design files for the 2-layer and 4-layer PCB versions.

```text
KiCad_2Layer/
└── 2-layer PCB project files

KiCad_4Layer/
└── 4-layer PCB project files
```

---

## Project Structure

```text
04_MCU_Datalogger/
│
├── README.md
│
├── KiCad_2Layer/
│   └── 2-layer PCB project files
│
├── KiCad_4Layer/
│   └── 4-layer PCB project files
│
├── BOM/
│   └── MCU_Datalogger_ibom.html
│
├── Datasheets/
│   ├── 21941.pdf
│   ├── ATMEGA328PAU_Microchip_Technology.pdf
│   └── DS1337S_Maxim_Integrated_Products.pdf
│
├── Gerbers/
│   └── Gerber and drill files
│
└── Images/
    ├── Schematic.png
    ├── PCB and 3D views
    └── Verification images
```

---

## What I Practiced

Through this project, I practiced:

- MCU-based PCB design
- ATmega328P-AU integration
- I²C bus design
- UART interface design
- ISP programming interface
- RTC integration
- EEPROM integration
- Crystal oscillator circuitry
- Connector and I/O design
- Schematic capture
- Component selection
- Footprint assignment
- 2-layer PCB layout
- 4-layer PCB layout
- PCB routing
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
