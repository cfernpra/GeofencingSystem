# Geofencing System for Arduino Nano  

## Project Overview  
This project implements a geofencing system designed to assist elderly individuals by monitoring their location using a GPS module. If the user moves outside a predefined safe zone, the system triggers visual (LED) notifications and logs the event for further actions.  

The system is built using an Arduino Nano, a GPS module, and Firebase integration for remote logging of location data.  


## Contents of This Repository  //TODO: to be implemented, currently all files are in main folder

- **`/src/`**: Contains all source code files:  
  - `GeofencingSystem.ino`: Main Arduino sketch.  
  - `GPS.h` & `GPS.cpp`: Manages GPS data acquisition and processing.  
  - `LED.h` & `LED.cpp`: Handles the LED indicator logic.  
  - `Timer.h` & `Timer.cpp`: Utility class for interval-based logic.  
  - `FirebaseConnection.h` & `FirebaseConnection.cpp`: Handles data logging to Firebase.  

- **`/docs/`**: Contains documentation files:  
  - User Manual (`User_Manual.pdf`).  
  - System Design Document (`System_Design.pdf`).  
  - Diagrams (UML, system architecture, etc.).  

- **`/extras/`**: Contains auxiliary files:  
  - Photographs of the hardware setup.  
  - Example test logs from the console.  

---

## Hardware Requirements  
- **Arduino Nano (ATmega328P, Old Bootloader)**.  
- **GPS Module** (GT-U7, could be used another one).  
- **LED** for visual notifications.  
- **Resistors** (220).  
- **USB cable** for programming and powering the Arduino.  
- **Optional**: Breadboard and jumper wires for prototyping.  

---

## Software Requirements  
1. **Arduino IDE**: Version 1.8.x or higher.  
   - Ensure the "Processor" option is set to `ATmega328P (Old Bootloader)` in the IDE.  
2. **Libraries**:  
   - [TinyGPS++](https://github.com/mikalhart/TinyGPSPlus): For GPS data parsing.  
   - [SoftwareSerial](https://www.arduino.cc/en/Reference/SoftwareSerial): For software-based serial communication.  
   - [FirebaseESP8266](https://github.com/mobizt/Firebase-ESP8266): For Firebase integration (if using the WiFi bridge on PC).  

---

## Setting Up the Hardware  
1. **Connect the GPS Module**:  
   - **TX pin of GPS** → **Pin 6** of Arduino Nano.  
   - **RX pin of GPS** → **Pin 7** of Arduino Nano.  
   - **GND pin of GPS** → **GND** on Arduino.  
   - **VCC pin of GPS** → **5V** on Arduino.  

2. **Connect the LED**:  
   - Positive terminal → **Pin 9** of Arduino Nano (through a resistor).  
   - Negative terminal → **GND** on Arduino.  

3. Use a breadboard for better prototyping and testing.  

---

## How to Compile and Upload  
1. Open the `GeofencingSystem.ino` file in the Arduino IDE.  
2. Go to **Tools > Board** and select `Arduino Nano`.  
3. Go to **Tools > Processor** and select `ATmega328P (Old Bootloader)`.  
4. Connect the Arduino Nano to the PC via USB.  
5. Click the **Upload** button to upload the code to the Arduino.  

---

## Using the System  

1. **Power the System**: Once the Arduino Nano is powered via USB or a battery, the system will initialize.  
2. **Monitor Console Output**: Open the Serial Monitor in the Arduino IDE at `9600 baud` to observe:  
   - GPS data: Latitude, Longitude, Distance from the safe zone.  
   - System status: Inside or outside the safe zone.  
3. **Observe LED Behavior**:  
   - **ON**: Outside the safe zone.  
   - **OFF**: Inside the safe zone.  

---

## Firebase Integration (Optional)  //TODO: to be implemented

If using Firebase for remote logging:  
1. Configure the PC as a WiFi bridge using the provided Python script in `/extras/WiFiBridge.py`.  
2. Edit `FirebaseConnection.cpp` to include your Firebase URL and authentication details.  
3. Ensure the Python script and the Arduino are running simultaneously.  

---

## Troubleshooting  
- **No GPS Data**: Ensure the GPS module has a clear view of the sky. Check connections.  
- **Unresponsive LED**: Verify the LED polarity and connections.  
- **Serial Monitor Issues**: Confirm the correct baud rate (`9600`).  

---

## Access the Code

The full implementation, including the class-based design and extended documentation, is also available on [GitHub](https://github.com/cfernpra/locator.git) in the `cpp_class_based` branch.


## Author  
Developed as part of a **Final Year Project** for Bachelor's Degree in Techniques for Software Development, focusing on assistive technologies for elderly individuals.  

For inquiries or support, contact: Carlos Fernandez Pradales.
