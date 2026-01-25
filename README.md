# AquaSOS – Intelligent Rescue Buoy

## Overview

**AquaSOS** is an intelligent rescue buoy designed to provide immediate flotation and rapid localization of a person in distress in water.  
The system is intended for deployment from aerial or surface drones, as well as for use as a modern safety device on ships and yachts.

The project is developed as a **group engineering project by 3rd-year students of Electronics and Telecommunications at the Faculty of Electronics, Telecommunications and Informatics (ETI), Gdańsk University of Technology**.

<img width="1536" height="1024" alt="Moduł elektroniki i pompowania (1)" src="https://github.com/user-attachments/assets/1452dce4-ea21-411a-8c91-0cca15186130" />
"* Important Note: This image is AI generated and is just for demonstration purposes. The final version may look different, but the functionality and the idea remains the same.

---

## Project Objective

The main objective of the AquaSOS project is to develop an autonomous rescue buoy that:

- automatically activates upon contact with water or impact on the water surface,
- inflates using a pressurized CO₂ cartridge to provide sufficient flotation,
- determines its position using a GNSS (GPS) receiver,
- transmits the distress location wirelessly (LoRa / SAR beacon–based communication),
- provides visual localization using a high-intensity LED visible at night and in adverse weather conditions.

---

## Principle of Operation

1. The buoy is deployed into the water, either by drone drop or manual activation.
2. A water contact sensor or inertial sensor detects immersion or impact.
3. The inflation mechanism is triggered, filling the flotation bladder with CO₂.
4. The electronic system switches to rescue mode:
   - the GNSS module acquires the position,
   - the communication module periodically transmits the location,
   - the visual signaling system is activated.
5. The transmitted position can be received by rescue services or a dedicated ground station.

---

## Technical Assumptions

### Mechanical Design

- flotation bladder volume: approximately **15 L**,
- minimum buoyant force: **100 N**,
- standard **33 g CO₂ cartridge**,
- electronics enclosure with **IP68** protection rating,
- resistance to freshwater and seawater environments,
- mechanical structure suitable for drone deployment.

### Electronic System

- low-power microcontroller (ESP32 / STM32, depending on hardware revision),
- GNSS module supporting GPS / GLONASS / Galileo,
- LoRa communication module,
- high-intensity LED with 360° diffuser for visual signaling,
- water contact sensor and 3-axis accelerometer,
- Li-ion battery (approximately **3–4 Ah**) with integrated BMS,
- USB-C charging interface,
- custom-designed PCB integrating all electronic subsystems.

### Firmware

- operating modes:
  - standby,
  - activation,
  - rescue operation,
- power management with deep-sleep functionality,
- control of:
  - inflation mechanism,
  - wireless communication,
  - visual signaling,
- periodic transmission of rescue position data.

---

## Context and Inspiration

AquaSOS draws inspiration from existing maritime rescue solutions, such as:

- SAR emergency beacons,
- “man overboard” signaling buoys (e.g., SOS Dan Buoy).

The project integrates their core functionalities into a compact, autonomous system suitable for rapid deployment and modern rescue scenarios.

---

## Project Status

The project is currently in the **engineering prototype stage**.

This repository contains:

- schematic diagrams and PCB design files,
- firmware source code,
- project documentation and presentation materials,
- conceptual and system-level design descriptions.

---
