# Safety-Mining-Helmet
Project Overview
Mining zones are among the most hazard-prone areas when it comes to fire incidents. This project introduces a helmet-mounted Fire Safety Alert System tailored for underground or remote mining zones. It enables real-time smoke detection, onsite alert display, and location tracking for fast emergency response.

Key Features
Real-Time Smoke Detection
Continuously monitors air quality using a gas/smoke sensor (like MQ-2 or MQ-135) to detect hazardous conditions.

Immediate Safety Alerts
Displays a "Not Safe" warning on an OLED display when smoke or toxic gas is detected, allowing miners to take immediate action.

Live GPS Tracking
Retrieves and displays the current GPS coordinates using a module like NEO-6M, helping workers or automated systems send exact location to the rescue teams.

Rescue-Oriented Design
Location info can be shared with emergency teams via verbal communication or future automation integrations.

Components Used
Component	Purpose
Smoke Sensor (MQ-2/MQ-135)	Detects fire smoke or gas leakage
OLED Display (0.96” I2C)	Shows status and coordinates
GPS Module (NEO-6M)	Provides real-time location tracking
Microcontroller (Arduino/ESP32/ESP8266)	Core controller for the system
Buzzer (optional - for expansion)	Audible alert (planned upgrade)
Power Source + Jumper Wires	Electrical supply and connections

How It Works
The smoke sensor monitors air quality continuously.

When harmful gases or smoke are detected:

The OLED screen shows:  Not Safe

The GPS module fetches and displays current latitude and longitude.

This data enables:

Workers to evacuate in time.

Quick relay of accurate location to emergency teams.

Usage
Assemble components on a helmet or portable unit.

Upload the firmware via Arduino IDE or PlatformIO.

Power the device and observe alerts under test conditions.

Use GPS data to simulate emergency location relay.

Future Improvements
Add a Buzzer for audio-based alerts.

Send SMS Alerts with GPS coordinates using GSM/GPRS modules.

Cloud Integration or SD Card Logging for incident history tracking and reports.

Helmet Optimization: Integrate all components into a rugged, lightweight module for real-world deployment.
