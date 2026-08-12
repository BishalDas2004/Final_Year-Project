# Project Overview:

Traditional irrigation systems often depend on manual watering or fixed schedules. Such methods may result in over-irrigation, under-irrigation, water wastage, and unnecessary human effort.This project proposes an IoT-based Smart Irrigation System that continuously monitors important environmental and soil parameters and automatically decides when irrigation is required.

The system uses an ESP32 as the central controller and collects information from:

- Soil Moisture Sensor
- DHT11 Temperature & Humidity Sensor
- Ultrasonic Water-Level Sensor
- Rain Sensor
- Soil pH Sensor

The collected data is processed locally by the ESP32. Depending on the environmental conditions, crop selection, soil pH, rainfall, and water availability, the system controls a DC water pump.When internet connectivity is available, sensor data is also sent to the Blynk IoT platform for remote monitoring, visualization, and notifications.The system is also designed to maintain its core irrigation functionality during internet outages.


# Objectives:

The main objectives of the project are:

1. Monitor soil moisture, temperature, humidity, rainfall, soil pH, and tank water level in real time.
2. Automate irrigation using an ESP32 microcontroller.
3. Reduce unnecessary water consumption.
4. Implement crop-specific irrigation parameters.
5. Use soil pH information to classify soil conditions.
6. Provide fertilizer recommendations based on soil pH.
7. Detect rainfall and prevent unnecessary irrigation.
8. Use weather forecast information for predictive irrigation.
9. Dynamically adjust irrigation duration according to environmental conditions.
10. Estimate and track water saved through rain-based irrigation skipping.
11. Detect sensor and pump-related faults.
12. Protect the pump from dry-run conditions.
13. Provide remote monitoring and alerts through Blynk.
14. Maintain local irrigation functionality even when internet connectivity is unavailable.



# Hardware Components:

1. ESP32 -	Main microcontroller and IoT communication
2. Capacitive Soil Moisture Sensor	- Measures soil moisture
3. DHT11	- Measures temperature and humidity
4. HC-SR04 Ultrasonic Sensor -	Measures water-tank level
5. YL-83 Rain Sensor -	Detects rainfall
6. Analog Soil pH Sensor -	Measures soil pH
7. L298N Motor Driver - Controls the DC pump
8. DC Submersible Pump	- Performs irrigation
9. LM2596 Buck Converter	- Provides regulated voltage
10. Breadboard - Prototype circuit assembly
11. DC Power Supply/Battery - System power

The project report describes the ESP32 as the central control unit responsible for sensor acquisition, processing, pump control, and IoT communication.

# Software & Technologies:

1. Programming
- C/C++
- Arduino IDE
2. Microcontroller 
- ESP32
3. IoT Platform 
- Blynk
4. APIs 
- OpenWeatherMap Weather API
5. Libraries
- WiFi.h
- BlynkSimpleEsp32.h
- HTTPClient.h
- ArduinoJson.h
- DHT.h


# Block Diagram:

<img width="600" height="450" alt="final_year_block_diagram" src="https://github.com/user-attachments/assets/035a2b35-a7fb-49f3-97dc-dd8497b180f6" />




        

       
        







