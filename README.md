# Smartwatch-Robotics-Ecosystem 🚀🚀

Sup! This is the main repository for our custom, interconnected hardware ecosystem project. We are building a custom smartwatch that uses touchless air gestures to change screens, and a finger-mounted micro joystick to pilot a 2WD robot chassis across the room. Everything talks over a fast, zero-router **ESP-NOW** wireless link. 

---

## 👥 The Team
*   **Chief Editor & Lead Researcher:** Ayan  
*   **Technical Layout & Hardware Integration:** Nilabh, Krishiv and Samridh

---

## 🗂️ Project Folders
*   📁 `1-Smartwatch-ESP32C3/` ➔ The wrist engine setup. Handles the mini 0.96" OLED face, APDS-9960 gesture waves, and glove controller data.
*   📁 `2-RobotChassis-Wroom/` ➔ The mobile rover base. Receives the speed vectors and runs the upgraded TB6612FNG motor driver.
*   📁 `3-SmartGlasses-Wroom/` ➔ Our sci-fi HUD project. Receives live telemetry and shows a radar tracking screen on a clear OLED panel.

---

## 📅 Roadmap & Level Guide

### 🟢 Level 1: The Workspace Check (First Blink)
*   Hook up our new microcontrollers to our Windows 10 Dell Inspiron 5520 laptop using a solid data cable.
*   Flash a simple 5-line C++ blink script to make sure the onboard blue test LEDs flash perfectly and the chips are alive.

### 🟡 Level 2: Local Sensor Reading
*   Plug our TTP223 touch pads, air-gesture sensor, and micro joystick into a breadboard.
*   Open up the Serial Monitor on the laptop to watch the raw analog values change live before typing any wireless code.

### 🟠 Level 3: Finding the MAC Addresses
*   Run a quick diagnostic sketch on our two receiver Wroom boards to print out their factory-set hardware MAC addresses.
*   Write those numbers down and paste them straight into our smartwatch sender setup file.

### 🔴 Level 4: The 2.4GHz Radio Link
*   Turn on the ESP-NOW communication protocol layers.
*   Send a dead-simple single character data packet over the air to make sure the boards do a clean wireless handshake without lag.

### 🚀 Level 5: Full Assembly & Integration
*   Add proportional differential steering mix code and hook up the HC-SR04 ultrasonic sensor for auto-braking alerts.
*   Mount the watch core electronics inside our bare metal Logues watch frame ring and link up the smart glasses HUD panel.

---

## 🔌 Pin Map Reference

### ⌚ Smartwatch & Glove Unit (ESP32-C3 Super Mini)
*   **0.96" OLED Face & APDS-9960 Wave Sensor:** Shared I2C Line (SDA: `GPIO 8`, SCL: `GPIO 9`)
*   **Bezel Click Touch Pad:** TTP223 Pin (`GPIO 5`)
*   **Fingernail Action Touch Pad:** TTP223 Pin (`GPIO 6`)
*   **Glove Micro Joystick X-Axis:** Analog Channel (`GPIO 0 / A0`)
*   **Glove Micro Joystick Y-Axis:** Analog Channel (`GPIO 1 / A1`)
*   **Target Painter Pointer:** 3.3V Laser Diode Module (`GPIO 2`)

### 🤖 Mobile Robot Rover (ESP32 Wroom)
*   **Upgraded TB6612FNG Motor Driver Pins:**
    *   `PWMA` (Left Speed) ➔ `GPIO 12`
    *   `AIN1` (Left Direction A) ➔ `GPIO 13`
    *   `AIN2` (Left Direction B) ➔ `GPIO 14`
    *   `BIN1` (Right Direction A) ➔ `GPIO 27`
    *   `BIN2` (Right Direction B) ➔ `GPIO 26`
    *   `PWMB` (Right Speed) ➔ `GPIO 25`
    *   `STBY` (Standby Pin) ➔ Wired directly to Wroom `3.3V`
*   **Front Collision Radar:** HC-SR04 Sensor (Trigger: `GPIO 32`, Echo: `GPIO 33`)
*   **Audio Signals:** Active Piezo Buzzer Pin (`GPIO 18`)

### 👓 Smart Glasses HUD (ESP32 Wroom)
*   **1.5" Transparent OLED Screen:** I2C Bus Array (SDA: `GPIO 21`, SCL: `GPIO 22`)

---

## ⚠️ Fixed Project Guardrails
*   💰 **Wallet Limit:** Strict hard cap budget of **2,500**. No overspending for the next 6-7 months! 
*   🔋 **Power Lines:** Smartwatch runs on a flat 3.7V LiPo through a 3.3V LDO regulator. Rover chassis uses dual 18650 lithium cells stepped down to 5V via a buck converter.
