# Roborumble-solo-innovator (Maleto Hlolane)

# ClimaAware - Child Safety Climate Door System

## Project Description
ClimaAware is a smart IoT safety device mounted on the side of the door that prevents children from going outside during dangerous weather. It monitors temperature and humidity and uses audio-visual alerts to warn parents and stop children.

Category: Sustainable Home & Child Safety / Climate Awareness

## Hardware Components
- ESP32 DevKit v1
- DHT22 Sensor (Temperature & Humidity)
- SSD1306 OLED Display (128x64)
- PIR Motion Sensor (HC-SR501)
- Green LED (SAFE)
- Red LED (NOT SAFE)
- 2x Buzzer (Buzzer 1: Slow Warning, Buzzer 2: Fast Kid Alert)
- Rocker Switch
- White Enclosure Box

## Software & Frameworks
- *Language:* C++ (Arduino)
- *IDE:* Arduino IDE 2.x / Wokwi Simulator
- *Framework:* Arduino Framework for ESP32
- *Libraries Required:*
    - DHT sensor library by Adafruit (v1.4.4)
    - Adafruit SSD1306 (v2.5.9)
    - Adafruit GFX Library (v1.11.9)

## How to Run the Code

### Option 1: Wokwi Simulator (For Judges)
1. Go to https://wokwi.com
2. Import diagram.json and ClimaAware.ino
3. Click Play
4. Change DHT22 temperature slider to test SAFE / NOT SAFE logic

### Option 2: Real Hardware
1. Install Arduino IDE
2. Install libraries listed above via Library Manager
3. Connect ESP32 via USB
4. Select Board: "ESP32 Dev Module"
5. Upload ClimaAware.ino
6. Power ON with rocker switch

## Control Logic / Programming Design

*Method:* Threshold-based Control + Finite State Machine (FSM)

*3 System States:*
1.  *SAFE STATE (Temp 18-30°C, Hum <80%):*
        - Green LED = ON
        - Red LED = OFF
        - Buzzer 1 = OFF, Buzzer 2 = OFF
        - OLED: "LED: Green | PIR: Clear"

2.  *NOT SAFE STATE (Temp <18°C or >30°C or Hum >80%):*
        - Green LED = OFF
        - Red LED = ON
        - Buzzer 1 = SLOW BEEP (warning to parents)
        - OLED: "LED: Red | NOT SAFE"

3.  *KID DETECTED STATE (PIR = HIGH while in NOT SAFE):*
        - Buzzer 2 = FAST BEEP (loud alert to stop child)
        - OLED: "PIR: KID!"
        - System loops until PIR = Clear

The system runs in a continuous loop, reading sensors every 2 seconds.

## File Structure
