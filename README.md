# Roborumble-solo-innovator (Maleto Hlolane)
# ClimaAware - Smart Child Weather Safety System

## 1. High-Level Summary of Solution

*What uhm i  doing?*
ClimaAware is a safety system that protects children from playing outside during dangerous weather conditions like extreme heat, cold, or high humidity that can cause heatstroke or illness.

*How are we building it?*
We are building it using an ESP32 microcontroller as the brain. The system uses:
- DHT22 sensor to monitor temperature and humidity in real-time
- PIR motion sensor to detect when a child tries to go outside
- SSD1306 OLED display to show live status
- Red/Green LEDs and 2 Buzzers for visual and sound alerts
- Rocker Switch (ON/OFF) and Emergency Stop Button for safety control

The system has 3 states: SAFE (Green LED), NOT SAFE (Red LED + slow buzzer), and KID DETECTED (Red LED + fast loud buzzer).

*Technology:* Wokwi Simulation, Arduino C++, ESP32 DevKit V1

## 2. Directory Map

This repository is organized into 3 accessible folders as per competition rules:

| Folder | Description |
| :--- | :--- |
| */Source Code* | Contains the main Arduino code (.ino) for the ESP32, including sensor reading, logic, and alert system. |
| */Designs* | Contains the Wokwi wiring diagram (diagram.json), circuit schematics, breadboard layout, and component images. |
| */Documentation* | Contains project explanation, component list, connection explanation, test results, and future improvements. |

## How to Run
1. Open the Wokwi project link in /Designs
2. Click PLAY
3. Change DHT22 temperature to test SAFE and NOT SAFE states
4. Trigger PIR sensor to test KID DETECTED alert
