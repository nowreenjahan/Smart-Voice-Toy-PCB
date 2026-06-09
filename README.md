# FunLearnLab: Smart Voice Learning Toy Main Board

## 1. Project Overview & System Requirements
Designed and engineered a production-ready, compact 2-layer main PCB for an offline-focused smart educational toy targeted at children aged 3–6

### Key Constraints & Requirements:
* **Form Factor:** Compact design constrained to 6cm x 6cm or 8cm x 8cm to seamlessly fit the toy enclosure.
* **Layer Count:** 4-Layer stackup implemented to preserve signal integrity, enhance Wi-Fi performance, stabilize camera feeds, and minimize audio noise.
* **Primary Processing:** ESP32-S3 microcontroller utilizing built-in Wi-Fi/Bluetooth, external flash/SD storage, and an external Audio Codec for offline voice processing.
* **Peripherals Controlled:** 3W/5W Speaker (Class-D Amp), MEMS Microphone, OV2640 Camera Module, Small LED Matrix/IPS Face Display, Dual DC Wheel Motors (DRV8833/L9110), and Physical Buttons.

## 2. Component Selection & Schematic Design
* **Processor Core:** Deployed the ESP32-S3 and integrated high-capacity flash storage to house local voice lessons, audio files, and LED animation profiles offline.
* **Audio Subsystem:** Combined a high-fidelity MEMS microphone for child voice pickup with a MAX98357A Class-D Audio Amplifier to drive the speaker efficiently without generating heavy thermal waste.
* **Motor Driver:** Used an H-bridge IC (L9110/DRV8833) to handle the dual side-wheel steering motors, ensuring the control lines were heavily decoupled from the logic power rails.

## 3. Custom Library Generation
* **Fine-Pitch Connectors:** Drafted custom FPC connector footprints for the OV2640 Camera and LED Display, ensuring tight pad tolerances to avoid solder bridging during automated assembly (PCBA).


## 4. PCB Layout & Routing Strategy
* **Noise Isolation:** Explicitly isolated the motor driver routing and high-current motor power traces away from the sensitive analog lines of the audio amplifier and MEMS microphone to prevent audible buzzing or distortion during toy movement.
* **Thermal Management:** Implemented thermal vias and solid copper pours underneath the camera zone to dissipate heat generated during continuous video processing.

## 5. Repository Structure
* `01_PCB_Requirements_English.md`: Full English translation of the design requirement sheet for cross-border manufacturing compatibility.
* `02_Schematics/`: Complete schematic sheets in PDF format.
* `03_Custom_Libraries/`: Custom footprint folders, symbols, and STEP models.
* `04_PCB_Layout_Designs/`: 2D/3D design layout assets.
* `05_Manufacturing/`: Production-ready Gerbers, Drill files, BOM, and CPL files.
* `06_Images/`: Project screenshots and 3D rendering profiles.
