# HuskyLens-Color-Responsive-LED

An embedded system project that utilizes real-time machine vision to control an RGB LED module based on dynamic chromatic detection using the HuskyLens AI Vision Sensor and Arduino.

---

## 🎯 System Objective

The primary objective of this project is to build an automated visual-feedback loop. When a specific color frame is identified by the HuskyLens vision sensor, a corresponding color signal is triggered on a Common Anode RGB LED via PWM/Digital outputs on the microcontroller.

* Red Target Detected: Triggers Red output on the LED.
* Green Target Detected: Triggers Green output on the LED.
* Blue Target Detected: Triggers Blue output on the LED.

---

## 🧰 Hardware Components

| Quantity | Component Description |
| :---: | :--- |
| 1 | HuskyLens AI Vision Sensor |
| 1 | Arduino Uno Microcontroller Unit |
| 1 | Common Anode RGB LED Module |
| 3 | Current-Limiting Resistors ($220\Omega$) |
| 1 | Solderless Breadboard |
| Set | Male-to-Male / Male-to-Female Jumper Wires |
| 1 | USB Communication/Power Cable |

---

## 🔍 Vision Sensor Technical Context (HuskyLens)

The HuskyLens is an integrated AI vision module built to perform localized machine learning tasks on edge devices. It offloads visual processing from the main controller and communicates directly over standard serial protocols (I2C / UART).

### Core Vision Capabilities
* Color Identification: Real-time extraction and matching of learned color profiles.
* Biometric & Face Recognition: Detection and verification of human faces.
* Target Classification & Tracking: Real-time movement tracking of designated objects.
* Autonomous Line Tracking: High-speed path determination for robotics.
* AprilTag Recognition: Marker identification for positioning and control.

---

## ⚡ Circuit Wiring Scheme

Communication between the HuskyLens and Arduino is configured via the I2C Protocol by default.

### Interconnection Table

| Source Device | Terminal | Destination | Arduino Pin | Notes |
| :--- | :---: | :--- | :---: | :--- |
| HuskyLens | VCC | Arduino | 5V | System Power |
| HuskyLens | GND | Arduino | GND | Common Ground |
| HuskyLens | TX | Arduino | A4 (SDA) | Serial Data Line |
| HuskyLens | RX | Arduino | A5 (SCL) | Serial Clock Line |
| RGB LED | Common (+) | Arduino | 5V | Anode Terminal |
| RGB LED | Red Anode | Arduino | Pin 9 | Inline $220\Omega$ Resistor |
| RGB LED | Green Anode | Arduino | Pin 8 | Inline $220\Omega$ Resistor |
| RGB LED | Blue Anode | Arduino | Pin 7 | Inline $220\Omega$ Resistor |

> Note: Because the module uses a *Common Anode* LED, driving a pin to LOW completes the circuit and illuminates the selected channel.

---

## 🎬 Hardware Execution Demonstration













https://github.com/user-attachments/assets/33f48545-d599-407f-b613-49a1a04a436f




The video file (`HuskyLenWithLed.MOV`) uploaded in the repository demonstrates the system detecting different colored targets and instantaneously switching the active LED spectrum.
