# Smart Cooktop: IoT-Enabled Automated Kitchen
An IoT-enabled cooktop prototype designed to enhance kitchen safety, efficiency, and precision through real-time monitoring and automation. Developed as part of the Microprocessors and Microcontrollers course at VIT Chennai, this project showcases the practical integration of embedded systems, IoT, and sensors in modern culinary applications.

---

## Key Features

- **Real-Time Overflow Detection & Prevention**
  - Ultrasonic Sensor (HC-SR04) detects liquid levels.
  - Automatically cuts off induction cooktop via **relay** and triggers a buzzer to prevent spills.

- **Accurate Temperature Monitoring & Control**
  - MLX90614 Infrared Sensor tracks food temperature.
  - Auto power cut-off at threshold (e.g., **80°C**) to avoid overheating/undercooking.

- **Automated Stirring System**
  - Motor-driven stirrer ensures uniform mixing.
  - Ideal for recipes requiring **continuous stirring**.

- **Smart Utensil Height Sensing**
  - Dynamically computes utensil height and food content level.
  - Predicts potential overflow before it happens.

- **Interactive OLED Display**
  - Real-time feedback: temperature, utensil height, and overflow status.

---

## Technologies Used

- **Microcontroller:** ESP32  
- **Programming Language:** Embedded C  
- **Sensors:**
  - Ultrasonic Sensor (HC-SR04)  
  - Adafruit MLX90614 IR Temperature Sensor  
- **Actuators:**
  - Relay Module  
  - DC Motor with L298N Driver  
- **Display:** 0.96" OLED (SSD1306)  
- **Development Environment:** Arduino IDE  

---

## Impact & Results

- Reduced boil-over incidents by ~45% in test scenarios.  
- Optimized MCU logic for **23% faster response time**.  
- Maintains temperature within **±1.2°C** for consistent cooking.  

---

## System Architecture

- **ESP32** as the control hub.  
- **Ultrasonic sensor** → Detects utensil/food height → Predicts overflow.  
- **Infrared sensor** → Tracks temperature → Relay cuts off heating if threshold exceeded.  
- **Motor + L298N driver** → Automated stirrer at programmed intervals.  
- **OLED display** → Shows real-time data for user monitoring.

---

## Visuals
- Prototype Snapshot:
  
  <img width="711" height="585" alt="image" src="https://github.com/user-attachments/assets/e238114b-57ec-4779-b134-1e0a1505d778" />
  
- Working Video:
  
https://drive.google.com/file/d/1sU43ZnGLtXPCUoEiKGSiYKSpHR6ugXGT/view?usp=drive_link

---

## Setup & Usage

### Hardware Assembly
- **Connect Ultrasonic Sensor**
  - Trig → GPIO 19  
  - Echo → GPIO 2  
- **Connect MLX90614 Sensor (I2C)**
  - SDA → GPIO 21  
  - SCL → GPIO 22  
- **Relay Module** → GPIO 23 (controls cooktop power)  
- **DC Motor + L298N Driver** → GPIO 25, 26 (motor control)  
- **OLED Display (SSD1306, I2C)**
  - SDA → GPIO 21  
  - SCL → GPIO 22  

---

### Software Setup
1. Install **Arduino IDE**.  
2. Add **ESP32 board support** in Arduino Boards Manager.  
3. Install required libraries:  
   - `Wire.h`  
   - `Adafruit_SSD1306.h`  
   - `Adafruit_MLX90614.h`  

---

### Flashing Firmware
1. Open `Final_Code.ino` in Arduino IDE.  
2. Select **ESP32 Dev Module** and correct **COM port**.  
3. Compile & upload the code.  

---

### Operation
- Power the system via USB/adapter.  
- Perform initial calibration using the **push button**.  
- Observe real-time data (**temperature, height, overflow alerts**) on the **OLED display**.  

---

## Future Work
- **Mobile App Integration** for remote control & monitoring.  
- **Voice Assistant Compatibility** (Alexa, Google Assistant).  
- **AI-based Food Type Recognition** for smart cooking profiles.  
- **Energy Consumption Monitoring** for efficiency tracking.  
- **Multi-Utensil Management** for simultaneous vessel control.  



