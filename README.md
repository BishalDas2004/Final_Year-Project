# Project Overview:

Traditional irrigation systems often depend on manual watering or fixed schedules. Such methods may result in over-irrigation, under-irrigation, water wastage, and unnecessary human effort.This project proposes an **IoT-based Smart Irrigation System** that continuously monitors important environmental and soil parameters and automatically decides when irrigation is required.

The system uses an **ESP32** as the central controller and collects information from:

- Soil Moisture Sensor
- DHT11 Temperature & Humidity Sensor
- Ultrasonic Water-Level Sensor
- Rain Sensor
- Soil pH Sensor

The collected data is processed locally by the ESP32. Depending on the environmental conditions, crop selection, soil pH, rainfall, and water availability, the system controls a DC water pump.When internet connectivity is available, sensor data is also sent to the **Blynk IoT platform** for remote monitoring, visualization, and notifications.The system is also designed to maintain its core irrigation functionality during internet outages.


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

<img width="560" height="432" alt="final_year_block_diagram" src="https://github.com/user-attachments/assets/035a2b35-a7fb-49f3-97dc-dd8497b180f6" />



# Key Features:

## 1. Automatic Irrigation

The ESP32 continuously monitors soil moisture and automatically controls the water pump whenever irrigation is required.


## 2. Soil Moisture Monitoring

A capacitive soil moisture sensor provides the primary input for determining whether the soil requires irrigation.


## 3. Real-Time Rain Detection

A rain sensor detects actual rainfall conditions.If rainfall is detected, irrigation can be paused or prevented to avoid unnecessary water usage.


## 4. Weather Forecast Integration

The system uses a weather API to check upcoming rainfall.The current implementation checks the next **12 hours** using four 3-hour forecast blocks.If rainfall is predicted, the irrigation decision can be overridden to conserve water.


## 5. Soil pH Monitoring

The pH sensor measures soil acidity/alkalinity.

The system classifies the soil into:
- Acidic
- Neutral
- Basic

For the `Others` crop mode, the pH classification also influences the soil moisture threshold.


## 6. Crop-Specific Irrigation

The user can select different crops from the Blynk interface.

Supported crops include:
- Rice
- Potato
- Wheat
- Onion
- Tomato
- Others

Each crop uses different moisture thresholds and base pump durations.


## 7. Fertilizer Recommendation

Based on measured soil pH, the system recommends:
- Fertilizer type
- Suggested brand
- Approximate quantity

The recommendation is displayed through the Blynk interface.


## 8. Water-Saving Analytics

When irrigation is skipped because of rainfall, the system estimates how much water would have been used.The estimated saved water is accumulated and displayed through the Blynk dashboard.


## 9. Fault Detection

The system checks for abnormal sensor readings and identifies possible faults involving:
- Soil moisture sensor
- DHT11
- Ultrasonic sensor
- pH sensor
- Rain sensor
- Pump

The fault status can be displayed through Blynk.


## 10. Tank Empty / Pump Protection

The ultrasonic sensor monitors the water reservoir.If the water level becomes critically low, the system can stop the pump and notify the user to prevent dry running.


## 📡 11. Offline Operation

Internet connectivity is not required for the basic irrigation function.

During offline operation:
- Sensors continue working.
- Local irrigation logic continues working.
- Pump control continues using local thresholds.
- Weather API functionality is unavailable.
- Blynk cloud synchronization is unavailable.

When connectivity is restored, cloud monitoring and weather functionality resume automatically.



        

       
        







