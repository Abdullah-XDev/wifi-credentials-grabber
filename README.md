# WiFi Credentials Grabber with OLED Display

A captive portal phishing tool for ESP32-S3 with SH1106 OLED display that mimics legitimate WiFi networks to capture credentials.

## Features

- Scan and display available WiFi networks
- Create evil twin access points for selected networks
- Capture WiFi passwords through fake authentication pages
- Real-time display on SH1106 OLED (128x64)
- Show selected network, last captured password, and last connected SSID
- Web-based management interface
- Automatic network rescan every 15 seconds

## Hardware Requirements

- ESP32-S3 Development Board
- SH1106 OLED Display (128x64, I2C)
- Jumper wires

## Pin Connections

| OLED Pin | ESP32-S3 Pin |
|----------|--------------|
| SDA      | GPIO 8       |
| SCL      | GPIO 9       |
| VCC      | 3.3V         |
| GND      | GND          |

## Software Requirements

- Arduino IDE or PlatformIO
- Required Libraries:
  - WiFi.h
  - DNSServer.h
  - WebServer.h
  - U8g2lib.h

## Installation

1. Clone this repository:
```bash
git clone https://github.com/Abdullah-XDev/wifi-credentials-grabber.git
