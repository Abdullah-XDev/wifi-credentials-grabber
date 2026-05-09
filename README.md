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
```
	2	Install required libraries in Arduino IDE:
	◦	Sketch → Include Library → Manage Libraries
	◦	Search and install "U8g2" by Oliver
	3	Select board: ESP32S3 Dev Module
	4	Update I2C pins in the code if needed:
cpp
#define OLED_SDA 8
#define OLED_SCL 9
##	5	Upload the code to your ESP32-S3
## Usage
	1	Power up the ESP32-S3
	2	Connect to the "XDev" WiFi network (password: 12345678)
	3	Open browser and navigate to 192.168.4.1
	4	Select target network from the list
	5	Click "Start EvilTwin" to create a fake AP
	6	Victims connecting to the fake AP will see a password prompt
	7	Captured passwords appear on both OLED display and web interface
## OLED Display Information
## The OLED screen shows:
	•	Selected AP: Currently targeted network
	•	Last Password: Most recently captured password
	•	Last Connected: SSID of the last successful authentication
## Web Interface Features
	•	List of available WiFi networks
	•	Select target network button
	•	Start/Stop Evil Twin toggle
	•	Real-time captured password display
## Security Notice
## ⚠️ IMPORTANT: This tool is for educational purposes and authorized security testing only. Unauthorized use against networks you don't own or have permission to test is illegal.
## How It Works
	1	Network Scanning: Device scans for nearby WiFi networks
	2	Evil Twin Creation: Creates a fake AP with selected SSID
	3	Captive Portal: Redirects victims to fake authentication page
	4	Credential Capture: Saves entered passwords
	5	Verification: Attempts to verify credentials with real network
	6	Display Update: Shows captured data on OLED screen
## Troubleshooting
## OLED not working:
	•	Check I2C connections
	•	Verify correct pins (SDA=8, SCL=9)
	•	Try different I2C addresses
## Can't connect to “XDev”:
	•	Ensure ESP32 is powered
	•	Check serial output for debug messages
	•	Reset the device
## No networks showing:
	•	Ensure WiFi antenna is connected
	•	Move closer to WiFi sources
	•	Check serial monitor for scan results

## Disclaimer
This software is provided for educational purposes only. The author is not responsible for any misuse or damage caused by this program. Always obtain proper authorization before testing networks.
## Author
Abdullah-XDev
## Version
1.0.0
