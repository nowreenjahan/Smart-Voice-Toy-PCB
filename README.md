# FunLearnLab: Smart Voice Learning Toy Main Board

## 1. Project Overview & System Requirements
[cite_start]Designed and engineered a production-ready, compact 4-layer main PCB for an offline-focused smart educational toy targeted at children aged 3–6[cite: 4, 5, 212]. 

### Key Constraints & Requirements:
* [cite_start]**Form Factor:** Compact design constrained to 6cm x 6cm or 8cm x 8cm to seamlessly fit the toy enclosure[cite: 204, 206, 208].
* [cite_start]**Layer Count:** 4-Layer stackup implemented to preserve signal integrity, enhance Wi-Fi performance, stabilize camera feeds, and minimize audio noise[cite: 212, 214, 215, 216, 217].
* [cite_start]**Primary Processing:** ESP32-S3 microcontroller utilizing built-in Wi-Fi/Bluetooth, external flash/SD storage, and an external Audio Codec for offline voice processing[cite: 37, 41, 42].
* [cite_start]**Peripherals Controlled:** 3W/5W Speaker (Class-D Amp), MEMS Microphone, OV2640 Camera Module, Small LED Matrix/IPS Face Display, Dual DC Wheel Motors (DRV8833/L9110), and Physical Buttons[cite: 47, 51, 54, 71, 72, 85, 95, 144].

## 2. Component Selection & Schematic Design
* [cite_start]**Processor Core:** Deployed the ESP32-S3 and integrated high-capacity flash storage to house local voice lessons, audio files, and LED animation profiles offline[cite: 37, 133].
* [cite_start]**Audio Subsystem:** Combined a high-fidelity MEMS microphone for child voice pickup with a MAX98357A Class-D Audio Amplifier to drive the speaker efficiently without generating heavy thermal waste[cite: 52, 54, 55].
* [cite_start]**Motor Driver:** Used an H-bridge IC (L9110/DRV8833) to handle the dual side-wheel steering motors, ensuring the control lines were heavily decoupled from the logic power rails[cite: 91, 95].

## 3. Custom Library Generation
* [cite_start]**Fine-Pitch Connectors:** Drafted custom FPC connector footprints for the OV2640 Camera and LED Display, ensuring tight pad tolerances to avoid solder bridging during automated assembly (PCBA)[cite: 244, 253].
* [cite_start]**Ruggedized USB-C:** Created a mid-mount USB-C footprint with extended through-hole mechanical shielding tabs to withstand rough handling by children[cite: 244, 252].
* [cite_start]**3D Integration:** Paired every custom footprint with an exact STEP model to perform strict physical clearance verification before manufacturing[cite: 219].

## 4. PCB Layout & Routing Strategy
* [cite_start]**Noise Isolation:** Explicitly isolated the motor driver routing and high-current motor power traces away from the sensitive analog lines of the audio amplifier and MEMS microphone to prevent audible buzzing or distortion during toy movement[cite: 244, 250].
* [cite_start]**Thermal Management:** Implemented thermal vias and solid copper pours underneath the camera zone to dissipate heat generated during continuous video processing[cite: 244, 248].
* [cite_start]**Antenna Optimization:** Kept the ESP32-S3 onboard antenna area clear of all copper and ground planes to optimize the RF path for parent app synchronization and stable live-view feeds[cite: 244, 251].

## 5. Repository Structure
* [cite_start]`01_PCB_Requirements_English.md`: Full English translation of the design requirement sheet for cross-border manufacturing compatibility[cite: 243].
* [cite_start]`02_Schematics/`: Complete schematic sheets in PDF format[cite: 219].
* [cite_start]`03_Custom_Libraries/`: Custom footprint folders, symbols, and STEP models[cite: 219].
* [cite_start]`04_PCB_Layout_Designs/`: 2D/3D design layout assets[cite: 219].
* [cite_start]`05_Manufacturing/`: Production-ready Gerbers, Drill files, BOM, and CPL files[cite: 219].
* `06_Images/`: Project screenshots and 3D rendering profiles.
