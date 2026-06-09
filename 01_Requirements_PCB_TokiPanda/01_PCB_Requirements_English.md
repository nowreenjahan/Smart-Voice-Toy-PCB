# Smart Voice Toy - PCB Design Requirement Document

## 1. Product Overview
FunLearnLab is a Smart Voice Learning Toy designed for children aged 3–6. The device operates primarily offline, utilizing preloaded educational modules: Voice Lessons, Quizzes, Stories, Rhymes, Bangla, English, Numbers, Islamic, and Science topics. 

The device integrates a Camera, Speaker, Microphone, LED Face Display, Wheel Movement, Remote Control, Wi-Fi, Bluetooth, and Parent App Integration. The PCB layout must be modular to support future feature additions and hardware upgrades.

## 2. Core PCB Requirements
The main PCB board must integrate the following hardware subsystems:
* Main Processor / MCU
* Speaker Amplifier Circuit
* Microphone Input Circuit
* Battery Charging & Power Management System (PMIC)
* Wi-Fi + Bluetooth Module
* Camera & LED Face Display Connectors
* Wheel Motor Driver Subsystem
* Physical Push Buttons & Remote Receiver Module
* USB-C Charging Port
* Internal Flash Storage / MicroSD Card Support
* Optional AI Expansion Port

## 3. Core Processor Selection
* **Selected Architecture:** ESP32-S3 + External Flash Memory + Audio Codec
* **Design Justification:** Lowest cost ceiling, robust native offline voice processing support, integrated Wi-Fi/Bluetooth, native camera parallel bus interface, and support for Over-the-Air (OTA) firmware updates.

## 4. Audio Subsystem
* **Speaker Output:** Support for 1x 3W or 5W speaker featuring clean, child-friendly audio output.
* **Amplifier IC:** Low-power Class-D hardware amplifier (Example: MAX98357A).
* **Microphone:** Bottom-port MEMS microphone featuring clear child-voice capture and passive noise reduction.
* **Target Features:** Voice playback, recording, response capture, interactive sound effects, and reward tracks.

## 5. LED Face Display
* **Animations Supported:** Multi-state expressions (Eyes animating, Happy, Thinking, Listening, Sleeping, Talking).
* **Hardware Interface:** Small LED Matrix, Small IPS Display (1.5" - 1.77"), or custom RGB LED Array.

## 6. Camera Module
* **Module Type:** ESP32 Camera Module compatibility (OV2640 Image Sensor).
* **Placement:** Positioned centrally directly above or in the middle of the LED face.
* **Features:** Front-facing orientation, basic child face detection, and parental live-feed streaming via app.

## 7. Locomotion & Motor Control
* **Drive System:** 2 side-wheel driven motors with 1 hidden support wheel.
* **Driver Hardware:** Small form-factor H-Bridge DC motor driver (Example: L9110 or DRV8833).
* **Locomotion Profiles:** Action paths mapped to Greeting, Speaking, Celebration, and Manual Remote control inputs.

## 8. Battery & Power Management
* **Battery Chemistry:** Rechargeable Lithium Battery (2500mAh - 4000mAh capacity).
* **Battery Life Targets:** 6–8 hours of continuous operational usage.
* **Charging Interface:** SMT/Mid-mount USB-C interface.
* **Power Controller ICs:** Dedicated battery charging circuit (TP4056 recommended), cell overcharge/discharge protection IC, and analog battery percentage monitoring lines tied to the MCU.

## 9. Connectivity & Wireless Profiles
* **Wi-Fi Applications:** Parent app data syncing, content library updates, cloud AI processing modes, and live camera feed streams.
* **Bluetooth:** Initial app pairing, remote controller connection, and network onboarding.
* **OTA Updates:** Reliable firmware flashing over local Wi-Fi.

## 10. Storage Capabilities
* **Capacity:** Minimum 8GB onboard non-volatile storage (16GB preferred).
* **Data Allocation:** Local storage for voice lessons, rhyme audio files, story logs, quiz audio banks, and LED interface animations.
* **Expansion:** Secondary MicroSD Card slot.

## 11. Physical Interface (Buttons)
* Dedicated inputs for: Main Talk Button, Volume Up (+), Volume Down (-), Repeat, Mode Change, and Master Power Toggle.
* Firmware logic handles Single Press, Long Press, and Double Press states.

## 12. Wireless Remote Controller
* Handheld remote controlling basic locomotion (Forward, Backward, Left, Right) and application states (Repeat, Volume Controls, Next Lesson, Story Mode, Sleep Mode).
* **Connectivity choice:** Bluetooth Remote preferred.

## 13. Parent App Integration Metrics
The layout must facilitate seamless MCU tracking of variables pushed to the parent app dashboard: battery metrics, total usage duration, current lesson progress, user child profiles, camera streaming access, wireless credential handshakes, and OTA notifications.

## 14. Smart Power Management
* **Power States:** Active, Idle, Sleep, Auto-Shutdown, and Low-Battery Warning profiles.
* **Timeout Logic:** If zero response is received from the child, the system prompts audibly 3 times before automatically placing the MCU and motor rails into Low-Power Sleep Mode.

## 15. Future Expansion Interfaces
Include low-profile connector headers on the PCB to facilitate rapid prototyping of next-gen features: Extra LED modules, higher-res cameras, touch/vibration sensors, NFC readers, or hardware AI acceleration modules.

## 16. Structural Board Guidelines
* **Target PCB Dimensions:** Ultra-compact 6cm x 6cm or 8cm x 8cm footprints to comply with toy shell clearances.
* **PCB Stackup Stack:**2-Layer board configuration to guarantee clean high-speed trace tracking, signal stability for the camera parallel bus, isolated audio return paths, and optimal wireless antenna matching.

## 17. Engineering Notes for Assembly (DFM / Noise Mitigation)
* **Audio Noise:** Maintain high spatial clearance between noisy motor traces and analog microphone traces to avoid audio distortion during wheel rotation.
* **Thermal Mitigation:** Mitigate heat generation around the OV2640 camera processing zone using dedicated copper pouring.
* **Safety & Accessibility:** Heavy mechanical shielding on the USB-C charging tab to avoid mechanical breakoffs. Clear component reference designators and silk-screen labeling to support simplified assembly at overseas manufacturing houses.
