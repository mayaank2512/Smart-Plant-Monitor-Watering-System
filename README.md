# Smart Plant Monitor & Automatic Watering System

## Overview

This project is a smart system to monitor soil moisture (and optionally temperature, humidity, light) for a plant, plus automatically water when needed. It also provides a dashboard for remote monitoring and manual override.

---

## Features

- Read soil moisture and determine when the plant needs watering  
- (Optional) Read temperature, humidity, light level  
- Automatic control of a water pump or solenoid valve  
- Remote monitoring via dashboard (web/app)  
- Manual override from dashboard  
- Optional alerts (SMS / push / email) when soil is too dry or water reservoir is low  

---

## Components

Here is a list of hardware & software you’ll need.

### Hardware

| Component | Quantity | Purpose |
|---|---|---|
| ESP32 (or ESP8266) development board | 1 | Microcontroller with WiFi |
| Soil moisture sensor (capacitive preferred) | 1 | Measures soil moisture |
| Relay module (5V or appropriate for pump) | 1 | Switches the pump on/off |
| Water pump or solenoid valve | 1 | To water the plant |
| (Optional) DHT11 / DHT22 sensor | 1 | To measure temperature & humidity |
| (Optional) Light sensor / LDR or BH1750 | 1 | To measure ambient light level |
| (Optional) Water level sensor or float switch | 1 | To detect water reservoir level |
| Power supply (5V / 12V as needed) | ‑ | Powers board + pump etc. |
| Wires, breadboard / PCB, enclosure | ‑ | For connections and mounting |

### Software

- Arduino IDE (or PlatformIO) for ESP32 firmware  
- Libraries:  
  ‑ WiFi (for networking)  
  ‑ HTTPClient / MQTT library (if using MQTT)  
  ‑ JSON library (if sending data in JSON)  
  ‑ Sensor libraries: e.g. DHT, BH1750 etc.  
- (Optional) Backend: a server or cloud service (Firebase, AWS IoT, or your own REST / MQTT server)  
- (Optional) Frontend dashboard: web app (React, Vue, plain HTML/JS), mobile app (if desired)  

---

## Wiring / Circuit Diagram

```text
+---------------------+
|      ESP32          |
|                     |
| GPIO (Analog) ---- Soil Moisture Sensor
| GPIO ---------------- Relay Module ------------ Pump / Valve
| GPIO -------------- DHT / other sensors (if used)
| 5V / GND ------------- common power rails
+---------------------+

Also:  
- Relay module needs appropriate power (5V or as required)  
- Pump: consider external power supply if current draw is large  
- (Optional) Water level sensor in the reservoir, with one wire to water level, another to ground  

