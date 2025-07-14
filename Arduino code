#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>
#include <TinyGPS++.h>
#include <SoftwareSerial.h>
#define pow1 7
#define gas A0
// Pin definitions for GPS
SoftwareSerial ss(4, 3);  // RX, TX (GPS module on pins 4 and 3)

// Create an OLED display object (128x64)
#define SCREEN_WIDTH 128
#define SCREEN_HEIGHT 64
#define OLED_RESET    -1
Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &Wire, OLED_RESET);

// Create a TinyGPS++ object
TinyGPSPlus gps;

void setup() {
  // Start serial communication for debugging
  Serial.begin(9600);
  
  // Start GPS communication
  ss.begin(9600);
  pinMode(gas,INPUT);
  pinMode(pow1,OUTPUT);
  // Initialize the OLED display
  if (!display.begin(SSD1306_SWITCHCAPVCC, 0x3C)) {
    Serial.println(F("SSD1306 allocation failed"));
    for (;;);
  }
  display.display();  // Initialize display
  delay(2000);  // Pause for 2 seconds
}

void loop() {
  // This sketch displays the GPS coordinates on the OLED display.
  digitalWrite(pow1,HIGH);
  // Listen for new GPS data
  while (ss.available() > 0) {
      gps.encode(ss.read()); 
      // Get the latitude and longitude
      double latitude = gps.location.lat();
      double longitude = gps.location.lng();
      int gs=analogRead(gas); bn b
      // Clear the display
      display.clearDisplay();
      
      // Display Latitude and Longitude on OLED
      display.setTextSize(1);      // Normal text size
      display.setTextColor(SSD1306_WHITE); // White text
      display.setCursor(0, 0);     // Start at the top-left corner
      display.print("Latitude: ");
      display.println(latitude, 6);  // Show latitude with 6 decimal places
      
      display.setCursor(0, 20);    // Next line
      display.print("Longitude: ");
      display.println(longitude, 6);
      display.print("GAS: ");
      display.println(gs);
      display.display(); b
  }
}
