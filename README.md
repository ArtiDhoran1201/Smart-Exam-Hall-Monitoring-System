# Smart Exam Hall Monitoring and Management System

## 📌 Overview

The **Smart Exam Hall Monitoring and Management System** is an embedded system designed to automate examination timing, environmental monitoring, and examination hall management.

The system is developed using the **LPC2148 ARM7 microcontroller** and integrates RTC, LCD, 4×4 keypad, multiplexed 7-segment displays, LM35 temperature sensor, LEDs, buzzer, and external interrupts.

It helps reduce manual timing errors and provides secure and real-time examination monitoring.

---

## 🎯 Objectives

- Display current RTC date and time on LCD.
- Display room temperature using LM35.
- Configure examination duration using a 4×4 keypad.
- Implement examination countdown timing.
- Display remaining examination time using two multiplexed 7-segment displays.
- Provide Green, Yellow, and Red LED indications.
- Implement password-protected configuration using External Interrupt 0.
- Provide Pause/Resume functionality using External Interrupt 1.
- Automatically record examination start and end time using RTC.
- Reduce manual timing errors in examination management.

---

## ✨ Features

- 🔐 Password-protected configuration
- ⏰ RTC-based time and date management
- ⏳ Automatic examination countdown
- ⏸️ Pause and Resume functionality
- 🌡️ Real-time room temperature monitoring
- 🔢 Two-digit multiplexed 7-segment countdown display
- 💡 LED-based examination status indication
- 🔊 Buzzer indication when examination ends
- ⌨️ 4×4 keypad for password and configuration
- 🖥️ LCD display for time, temperature, and examination status

---

## 🔄 Project Workflow

### 1. Normal Monitoring

Before the examination starts, the LCD continuously displays the current RTC date and time along with the room temperature measured using the LM35 sensor.

### 2. Secure Configuration

The invigilator presses **Switch-1 connected to External Interrupt 0**.

The system enters a secured configuration mode and asks for the admin password through the 4×4 keypad.

If the password is correct, the invigilator can:

- Configure RTC date and time
- Set examination start time
- Configure examination duration

If the password is incorrect, access is denied and the system returns to normal monitoring mode.

### 3. Examination Start

When the configured examination start time is reached:

- The RTC records the examination start time.
- The examination countdown starts.
- Remaining examination time is displayed on the LCD.
- Two multiplexed 7-segment displays show remaining minutes.

### 4. Examination Status Indication

The system provides visual alerts based on the remaining examination time.

| Remaining Time | Indication |
|---|---|
| More than 10 minutes | Green LED |
| Final 10 minutes | Yellow LED |
| Last 1 minute | Red LED |
| 00 minutes | Buzzer |

### 5. Pause / Resume

**Switch-2 connected to External Interrupt 1** is used for Pause/Resume.

- Press once → Countdown pauses.
- Press again → Countdown resumes from the exact point where it was paused.

This can be useful during unexpected disturbances, technical issues, or official announcements.

### 6. Examination Completion

When the countdown reaches zero, the buzzer is activated to indicate the end of the examination session.

The RTC can also be used to record the examination end time.

---

## 🧩 Hardware Requirements

- LPC2148 ARM7 Microcontroller
- 16×2 LCD
- 4×4 Matrix Keypad
- Switches
- Two 7-Segment Displays
- LM35 Temperature Sensor
- LEDs
- Buzzer
- USB-UART Converter / DB-9 Cable

---

## 💻 Software Requirements

- Embedded C Programming
- Keil µVision
- Flash Magic
- Proteus for simulation

---

## 🏗️ System Architecture
<img width="1312" height="1199" alt="image" src="https://github.com/user-attachments/assets/e0f0633f-91b8-408b-913e-dfc3e70a588a" />

The system consists of the following major modules:

- LPC2148 Microcontroller
- RTC
- LCD
- 4×4 Keypad
- ADC
- LM35 Temperature Sensor
- 7-Segment Display
- LEDs
- Buzzer
- External Interrupts

---

## 📁 Project Structure

```text
Smart-Exam-Hall-Monitoring-System/
│
├── inc/
│   ├── adc.h
│   ├── adc_defines.h
│   ├── all_macros.h
│   ├── defines.h
│   ├── delay.h
│   ├── io_defines.h
│   ├── kpm.h
│   ├── kpm_defines.h
│   ├── lcd.h
│   ├── lcd_defines.h
│   ├── lm35.h
│   ├── rtc_default.h
│   ├── rtc_defines.h
│   ├── seg.h
│   ├── seg_defines.h
│   └── types.h
│
└── src/
    ├── adc.c
    ├── ca2seg_mux.c
    ├── delay_def.c
    ├── kpm.c
    ├── lcd.c
    ├── lm35.c
    ├── main.c
    ├── password.c
    ├── project_declarations.c
    └── rtc_default.c
```

---

## 🌡️ Temperature Monitoring

The **LM35 temperature sensor** provides an analog temperature signal.

The LPC2148 ADC converts this analog signal into digital data, and the calculated temperature is displayed on the LCD.

---

## 🔐 Password Protection

The system uses a password-protected configuration mode.

The password is entered through the **4×4 matrix keypad** before allowing the invigilator to modify:

- RTC date
- RTC time
- Examination start time
- Examination duration

---

## 🛠️ Development Environment

| Item | Details |
|---|---|
| Microcontroller | LPC2148 |
| Processor | ARM7 |
| Programming Language | Embedded C |
| IDE | Keil µVision |
| Simulation | Proteus |
| Flashing Tool | Flash Magic |
| Display | 16×2 LCD |
| Input | 4×4 Matrix Keypad |
| Temperature Sensor | LM35 |
| Time Source | RTC |

---

## 📌 Applications

- Educational institutions
- Examination halls
- Automated examination management
- Classroom monitoring systems
- Embedded-based time management systems

---

## 🚀 Future Scope

- Data logging for multiple examinations
- PC/mobile monitoring interface
- Automatic result/report generation
- Centralized examination monitoring
- Additional environmental sensors
- Real-time communication with a monitoring server

---

## 👩‍💻 Project

**Smart Exam Hall Monitoring and Management System**

**Controller:** LPC2148 ARM7 Microcontroller  
**Language:** Embedded C
