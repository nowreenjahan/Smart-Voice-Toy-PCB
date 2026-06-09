# FunLearnLab: Smart Voice Learning Toy Main Board

## 1. Project Overview & System Requirements
Designed and engineered a production ready, compact 2-layer main PCB for a smart educational toy targeted at children aged 3–6. 

### Key Constraints & Requirements:
* **Form Factor:** Compact design constrained to 6cm x 6cm or 8cm x 8cm to seamlessly fit the toy enclosure.
* **Layer Count:** 2-Layer stackup required to preserve signal integrity, enhance Wi-Fi performance, stabilize camera feeds, and minimize audio noise.
* **Primary Processing:** ESP32-S3 microcontroller utilizing built-in Wi-Fi/Bluetooth, external flash/SD storage, and an external Audio Codec for offline voice processing.
* **Peripherals Controlled:** 3W/5W Speaker (Class-D Amp), MEMS Microphone, OV2640 Camera Module, Small LED Matrix/IPS Face Display, Dual DC Wheel Motors (DRV8833/L9110), and Physical Buttons.

## 2. Component Selection & Schematic Design
* **Processor Core:** Deployed the ESP32-S3 and integrated high-capacity flash storage to house local voice lessons, audio files, and LED animation profiles offline.
* **Audio Subsystem:** Combined a high-fidelity MEMS microphone for child voice pickup with a MAX98357A Class-D Audio Amplifier to drive the speaker efficiently without generating heavy thermal waste.
* **Motor Driver:** Used an H-bridge IC to handle the dual side-wheel steering motors, ensuring the control lines were heavily decoupled from the logic power rails.

## 3. Custom Library Generation
* **Pitch Connectors:** Drafted custom FPC connector footprints for the OV2640 Camera and LED Display, ensuring tight pad tolerances to avoid solder bridging during automated assembly (PCBA).
* **3D Integration:** Paired every custom footprint with an exact STEP model to perform strict physical clearance verification before manufacturing.

## 4. PCB Layout & Routing Strategy
* **Noise Isolation:** Explicitly isolated the motor driver routing and high-current motor power traces away from the sensitive analog lines of the audio amplifier and MEMS microphone to prevent audible buzzing or distortion during toy movement.

## 5. Repository Structure
* `01_Design_Requirements/`: The original client engineering specifications document.
* `02_Schematic_Outputs/`: Complete schematic sheets in PDF format.
* `03_Custom_Libraries/`: Custom footprint folders, symbols, and STEP models.
* `04_PCB_Layout_Design/`: 2D design layout assets.
* `05_Manufacturing_Files/`: Production-ready Gerbers, Drill, BOM, and CPL files.
* `06_Images/`:Images of the schematic and PCB Board
