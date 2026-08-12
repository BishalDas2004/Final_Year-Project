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



# Block Diagram:

<img width="556" height="424" alt="final_year_block_diagram" src="https://github.com/user-attachments/assets/035a2b35-a7fb-49f3-97dc-dd8497b180f6" />



# How the System Works:

The general operating sequence is:

                  
START\n
  │\n
  ▼\n
Initialize ESP32 and Sensors\n
  │\n
  ▼\n
Attempt Wi-Fi Connection\n
  │\n
  ├───────────────┐\n
  │               │\n
Online          Offline\n
  │               │\n
  ▼               ▼\n
Blynk/API       Local Mode\n
  │               │\n
  └───────┬───────┘\n
          ▼\n
Read Sensors\n
          │\n
          ▼\n
Check Sensor Faults\n
          │\n
          ▼\n
Check Water Tank Level\n
          │\n
          ▼\n
Read Soil Moisture\n
          │\n
          ▼\n
Check Rain Sensor\n
          │\n
          ▼\n
Check Weather Forecast\n
          │\n
          ▼\n
Check Selected Crop\n
          │\n
          ▼\n
Evaluate Soil pH\n
          │\n
          ▼\n
Calculate Irrigation Requirement\n
          │\n
       ┌──┴──┐\n
       │     │\n
      NO    YES\n
       │     │\n
       │     ▼\n
       │  Check Rain\n
       │     │\n
       │  ┌──┴──┐\n
       │  │     │\n
       │ Rain  No Rain\n
       │  │     │\n
       │  ▼     ▼\n
       │ Skip  Pump ON\n
       │       │\n
       │       ▼\n
       │  Dynamic Runtime\n
       │       │\n
       └───────┘\n
          │\n
          ▼\n
   Update Blynk / Analytics\n
          │\n
          ▼\n
        LOOP\n







