# Anti-Theft Vehicle Tracking System

This project is an IoT-based anti-theft vehicle tracking system built using Arduino + GPS + LCD for location tracking and ESP8266 modules for wireless communication, vehicle alarm, and driver keychain alerts.

---

## Features
- Real-time GPS tracking (latitude & longitude).
- LCD display showing live coordinates and system status (STARTED/STOPPED).
- Push-button to toggle vehicle security status.
- Buzzer feedback when toggling security mode.
- Wireless data transfer using ESP-NOW (no internet required).
- Vehicle alarm buzzer if GPS transmitter stops sending data.
- Driver keychain unit with buzzer to alert the owner of theft or tampering.

---

## Hardware Requirements
Arduino Uno/Nano (for transmitter)  
ESP8266 NodeMCU / Wemos D1 Mini (for in-vehicle receiver)  
ESP8266 NodeMCU / Wemos D1 Mini (for driver keychain)  
GPS Module (Neo-6M or compatible)  
16x2 LCD Display  
Push Button Switch  
Buzzer (x3: Arduino feedback, vehicle alarm, keychain alert)  
Connecting wires & breadboard  

---

## Code Files
1. `AntiTheft_Transmitter.ino`  
   Runs on Arduino.  
   Reads GPS coordinates.  
   Displays location and system status on LCD.  
   Sends data periodically via Serial/ESP8266.  

2. `AntiTheft_Receiver.ino`  
   Runs on ESP8266 (inside the vehicle).  
   Uses ESP-NOW for wireless communication.  
   Receives data from Arduino/other ESPs.  
   Activates buzzer if data is not received for a set time (security alert).  


---

## How It Works
1. Arduino (Transmitter)  
   Continuously reads GPS location.  
   Displays data on LCD.  
   Sends location and system status every ~15 seconds.  

2. ESP8266 Receiver (Vehicle Alarm)  
   Listens for data via ESP-NOW.  
   If no data is received for more than 5 seconds, buzzer alarm in vehicle is triggered.  

3. ESP8266 Keychain Unit  
   Always listens for alerts from the vehicle receiver.  
   Sounds buzzer in the driver’s keychain when theft or tampering is detected.  


## Example Output
LCD Display:  



## Attachments

![AntiTheftWorkingModel](https://github.com/user-attachments/assets/239991bd-b4f8-4acb-a0e3-c918c9cef018)
![AntiTheftOutput](https://github.com/user-attachments/assets/534655ee-a9ce-4f80-a725-5d91953fe90f)





