# 🎓 **Smart Exam Hall Monitoring & Management System**

A smart embedded system designed to monitor and manage examination activities using an ARM7-based controller. The system provides real-time examination timing, temperature monitoring, countdown indication, admin configuration, and emergency pause/resume control.

## 🎯 Objective

The main objective of this project is to develop a smart examination hall monitoring system that helps invigilators manage examination time efficiently, monitor the hall temperature, and handle emergency situations using an embedded system.

The system reduces the need for manual time tracking and provides clear visual and audio indications during the examination.

## ✨ Features

• ⏱️ **Real-Time Clock Display**  
  Displays the current time, date, and day on a 16×2 LCD using the RTC.

• 🔢 **Exam Duration Setting**  
  A 4×4 keypad allows the invigilator to enter and set the examination duration.

• ⏳ **Exam Countdown Timer**  
  Displays the remaining examination time using a multiplexed 7-segment display.

• 🟢 **Percentage-Based Time Indication**  
  Green, yellow, and red LEDs indicate the remaining examination time based on the percentage of time left.

• 🔴 **Low-Time Warning**  
  The red LED indicates that the examination is approaching its end.

• 🔔 **Buzzer Alert**  
  The buzzer activates during the final 5% of the examination time as a warning.

• 🌡️ **Temperature Monitoring**  
  An LM35 temperature sensor measures the examination hall temperature and displays the value on the LCD.

• 🔐 **Admin Configuration**  
  An admin mode allows authorized configuration of time, date, day, and examination duration.

• ⏸️ **Emergency Pause / Resume**  
  An emergency switch allows the invigilator to temporarily pause and resume the examination timer.

• 📺 **LCD-Based User Interface**  
  Provides menus, prompts, and system information through the 16×2 LCD.

## 🔧 Hardware Components

• LPC2148 ARM7 Development Board  
• 16×2 LCD  
• 4×4 Keypad  
• RTC (DS1307)  
• LM35 Temperature Sensor  
• 7-Segment Display  
• Green LED  
• Yellow LED  
• Red LED  
• Buzzer  
• Push Buttons / Switches  
• 5V Regulator  
• 9V DC Adapter

## 🔌 Hardware Configuration

| Component / Pin / Interface | Description | Function |
|-----------------------------|-------------|----------|
| 16×2 LCD Data               | P0.8 – P0.15 | 8-bit data communication |
| LCD RS                      | P0.20        | Register Select |
| LCD EN                      | P0.21        | Enable signal |
| 4×4 Keypad                  | P1.16 – P1.23 | Keypad input |
| 7-Segment Display           | P0.0 – P0.7  | Segment control |
| 7-Segment Digit Select      | P0.16, P0.17 | Digit selection |
| Green / Yellow / Red LEDs   | P2.0 – P2.2  | Examination time indication |
| Buzzer                      | P2.3         | Audio warning |
| RTC                         | I²C           | Time and date information |
| LM35                        | ADC           | Temperature measurement |
| Switch 1                    | EINT0         | Admin / configuration mode |
| Switch 2                    | EINT1         | Emergency pause / resume |

## 🧩 System Architecture

The system is built around the **LPC2148 ARM7 microcontroller**, which acts as the main controller.

The controller interfaces with:

**Input Devices**

• 4×4 Keypad  
• LM35 Temperature Sensor  
• Admin Switch  
• Emergency Switch  

**Processing**

• LPC2148 ARM7 Controller  
• Timer  
• ADC  
• Interrupts  
• RTC Interface  

**Output Devices**

• 16×2 LCD  
• 7-Segment Display  
• Green LED  
• Yellow LED  
• Red LED  
• Buzzer

## 💻 Software & Tools

• **Programming Language:** Embedded C  
• **Microcontroller:** LPC2148 ARM7  
• **IDE:** Keil µVision 4  
• **Simulation Software:** Proteus  
• **Communication Interface:** I²C  
• **Temperature Interface:** ADC  
• **Display:** 16×2 LCD and 7-Segment Display

## 🧩 Block Diagram

<img width="1312" height="1199" alt="image" src="https://github.com/user-attachments/assets/54f98a80-996e-4d77-b9ac-5d2d5140eed8" />

## ⚙️ Working

The system starts by initializing the LPC2148 ARM7 microcontroller and all connected peripherals such as the LCD, RTC, keypad, ADC, timer, 7-segment display, LEDs, buzzer, and interrupts.

The RTC provides the current time, date, and day, while the LM35 temperature sensor measures the examination hall temperature. These values are displayed on the 16×2 LCD.

When EINT0 (Switch-1) is triggered, the system enters the admin configuration mode. After successful authentication, the administrator can set or modify the RTC information and examination duration using the 4×4 keypad.

Once the examination duration is set, the examination can be started. The system begins the countdown and displays the remaining time on the 7-segment display.

During the examination, the remaining time is continuously monitored:

• 🟢 **100%–50%** → Green LED  
• 🟡 **50%–25%** → Yellow LED  
• 🔴 **25%–5%** → Red LED  
• 🔔 **Final 5%** → Red LED + Buzzer  

If an emergency occurs, EINT1 (Switch-2) allows the invigilator to pause and resume the examination timer.

When the countdown reaches 0%, the examination is completed and the system provides the corresponding end indication.

This allows the system to provide automatic examination time management, temperature monitoring, visual warnings, audio alerts, and emergency control with minimal manual intervention.

## 🔄 Project Flow

<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/f87c3b93-29b0-438d-b23f-10b64774bd22" />

# ✅ Advantages

• ⏱️ Reduces manual examination-time monitoring  
• 🚦 Provides visual time indication  
• 🔔 Provides audible warning near examination completion  
• 🌡️ Provides temperature monitoring  
• 🔐 Provides password-protected configuration  
• 🚨 Supports emergency pause and resume    
• 💻 Tested using both Proteus and actual hardware  
• 🧩 Modular Embedded C implementation

# ⚠️ Limitations

• Temperature measurement depends on sensor placement.  
• No automatic student identification is included.

# 🏫 Applications

The system can be useful in:

• 🎓 Schools  
• 🏫 Colleges and Universities  
• 📝 Examination Centers  
• 📚 Training Institutes  
• 🏢 Other controlled examination environments

# 🚀 Future Scope

• 🌐 **IoT Connectivity**  
  Enable remote monitoring of examination status.

• 📱 **Mobile Application**  
  Monitor exam progress and system status remotely.

• ☁️ **Cloud Data Logging**  
  Store examination start/end times and system data.

• 📷 **Camera Integration**  
  Enable visual monitoring of examination halls.

• 🤖 **AI-Based Monitoring**  
  Add intelligent monitoring and predefined suspicious-activity detection.

• 💾 **Event Logging**  
  Store pause/resume events, temperature readings, and examination timings.

• 🔋 **Battery Backup**  
  Provide uninterrupted operation during temporary power failures.

  ## 👩‍💻 Development & Developer Details

**Project:** Smart Exam Hall Monitoring & Management System

**Controller:** LPC2148 ARM7

**Language:** Embedded C

**IDE:** Keil µVision 4

**Simulation:** Proteus

**Developer:** Sathwika

**GitHub:** @damanisathwika
