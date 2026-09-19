# EXP 7 : INTERFACING A 16×2 LCD WITH ARDUINO USING AN I2C MODULE FOR SENSOR DATA DISPLAY


# AIM

To interface a **16×2 LCD display with Arduino using an I2C module** and display sensor data on the LCD.

# Objectives

- To understand the operation of a 16×2 LCD.
- To interface the LCD with Arduino using an I2C module.
- To reduce the number of GPIO pins required for LCD communication.
- To read sensor data using Arduino.
- To display the sensor readings on the LCD.

# Hardware / Software Tools Required

# Hardware

- Arduino UNO
- 16×2 LCD Display
- I2C LCD Module (PCF8574-based)
- DHT11 Temperature and Humidity Sensor
- Breadboard
- Jumper wires
- USB cable

# Software

- Arduino IDE
- Arduino C/C++ programming language
- LiquidCrystal_I2C library
- DHT sensor library

# Components

### 16×2 LCD
### I2C Module
### Circuit Connections
### I2C Communication
### Working Principle

1. The DHT11 sensor measures temperature and humidity.
2. Arduino reads the sensor values through the digital data pin.
3. The Arduino processes the received sensor data.
4. The processed values are sent to the LCD through the I2C interface.
5. The LCD displays the temperature on one line.
6. The humidity is displayed on the second line.
7. The readings are periodically updated.

# Arduino Program
```
#include <Adafruit_LiquidCrystal.h>

// Connect via I2C, default address is usually 0 or 0x27 in Tinkercad
Adafruit_LiquidCrystal lcd(0);

void setup() {
  // Initialize the LCD display size
  lcd.begin(16, 2);
  
  // Turn on the backlight
  lcd.setBacklight(HIGH);
  
  // 1. Move cursor to column 0, row 0 (the top row)
  lcd.setCursor(0, 0);
  
  // 2. Print your name here (Change "Your Name" to whatever you like!)
  lcd.print("GIRI");
}

void loop() {
  // Move cursor to column 0, row 1 (the second row)
  lcd.setCursor(0, 1);
  
  // Print seconds elapsed
  lcd.print("Time: ");
  lcd.print(millis() / 1000);
  
  // Small delay to prevent the screen from flickering
  delay(200); 
}

```

# Output

<img width="1902" height="1090" alt="Screenshot 2026-09-19 084435" src="https://github.com/user-attachments/assets/1bad17fb-6dcb-4f8e-ba75-da74e3057850" />

# Result

Thus, the **16×2 LCD was successfully interfaced with Arduino UNO using an I2C module**, and the name and timer were successfully displayed on the LCD. The experiment demonstrates the use of **I2C communication for efficient sensor-data display** in embedded and IoT applications.
