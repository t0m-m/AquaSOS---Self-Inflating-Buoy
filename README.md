# AquaSOS – Intelligent Rescue Buoy

## Overview

**AquaSOS** is an intelligent rescue buoy designed to provide immediate flotation and rapid localization of a person in distress in water.  
The system is intended for deployment from aerial or surface drones, as well as for use as a modern safety device on ships and yachts.

The project is developed as a **group engineering project by 3rd-year students of Electronics and Telecommunications at the Faculty of Electronics, Telecommunications and Informatics (ETI), Gdańsk University of Technology** in collaboration with **AREX Automation and Measurement Devices Plant Sp. z o. o.** from Gdynia.

<img width="1536" height="1024" alt="Moduł elektroniki i pompowania (1)" src="https://github.com/user-attachments/assets/1452dce4-ea21-411a-8c91-0cca15186130" />
Important Note: This image is AI generated and is just for demonstration purposes. The final version may look different, but the functionality and the idea remains the same.

---
## Schematic

<img width="1790" height="1181" alt="image" src="https://github.com/user-attachments/assets/afcc4ffd-4ba2-40ed-902f-bb73206da9d3" />

---
## PCB

<img width="1380" height="1273" alt="image" src="https://github.com/user-attachments/assets/66e29e3a-8488-46a8-abe5-47cba2b61d7d" />

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

There are two main ways in which AquaSOS can be deployed, either 'by hand' or dropped from a flying or swimming drone using payload release mechanism which we are also developing.

1. Deployment by hand:
   First, the user needs to hold waterproof button on the side of the buoy for 3 seconds, after which acoustic signal informs the user of the arming of the system. Then user tossess AquaSOS to the drowning person. The accelerometer detects the impact on the surface of the water and immediately triggers inflating mechanism.

2. Deployment from a drone:
   In this case, the buoy is equipped with a hall sensor, and the payload release mechanism is equipped with strong magnet. When AquaSOS sits in the 'bomb bay', hall sensor detects the magnet and the system is not armed. After opening bay doors, the buoy falls and the sensor stops detecting magnetic field. When it doesn't detect the magnetic field for a couple of seconds, it arms. Then the accelerometer detects impact on the surface of the water and starts inflating AquaSOS.

After inflation Aquasos starts obtaining (through GNSS antenna on-board) and broadcasting its position as well as a distress signal using LoRa FPC antenna mounted to the case. It also activates LED light for easy identification and visibility in night and severe weather conditions.
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
- Integrated nRF52840 + GNSS + LoRa module Wio - WM1110
- high-intensity LED for visual signaling,
- 3-axis accelerometer,
- Li-ion battery (in the prototype we used normal drone battery pack that will be charged using external charger, however in the future we plan to fully integrate tha battery and charging circuit within the   main PCB),
- USB-C data interface,
- Additional SWD pins serving as backup if USB-C fails,
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

AquaSOS aims to significantly shorten the time it takes to reach a drowning victim by enabling the buoy to be attached to flying drones, which can reach the victim faster than any human rescuer.

AquaSOS draws inspiration from existing maritime rescue solutions, such as:

- SAR emergency beacons,
- “man overboard” signaling buoys (e.g., SOS Dan Buoy).

The project integrates their core functionalities into a compact, autonomous system suitable for rapid deployment and modern rescue scenarios.

---

## Project Status

The project is currently in the **engineering prototype stage**.

This repository will contain:

- schematic diagrams and PCB design files,
- firmware source code,
- project documentation and presentation materials,

---
