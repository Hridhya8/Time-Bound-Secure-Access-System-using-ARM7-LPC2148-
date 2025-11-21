# Time-Bound-Secure-Access-System-using-ARM7-LPC2148-
Secure multi-user access control with real-time authentication, time-window enforcement, temperature monitoring, and an enhanced Admin configuration mode.

📌 Project Overview

The Time-Bound Secure Access System is an embedded security solution that grants access to users only within their predefined time intervals. It uses LPC2148 ARM7 microcontroller, RTC, keypad, and LM35 temperature sensor.

Features include:

Multi-user authentication (User ID + PIN)

Real-time access validation using RTC

Live temperature monitoring on LCD

Admin mode enabled through a secure physical switch sequence

Admin can edit RTC & user time windows

Visual and audible alerts using LEDs & buzzer

Ideal for labs, server rooms, research facilities, restricted areas, and shift-based access.
Hardware Used
Component	Purpose
LPC2148 ARM7 Controller	Core processing & peripheral control
16×2 LCD	System display, prompts, temperature
4×4 Keypad	User ID & PIN entry
LM35 Temperature Sensor	Room temperature monitoring
RTC (Inbuilt)	Real-time access validation
LEDs	Access status
Buzzer	Error / warning alerts
Admin Activation Switch	Triple-press activation for Admin mode

💾 Software & Tools
Embedded C

Keil µVision

Flash Magic

🔐 Authentication Flow

1️⃣ Enter User ID

LCD → “Enter User ID”
If ID invalid → reject.

2️⃣ Enter PIN

LCD → “Enter PIN”
If PIN invalid → reject.

3️⃣ RTC Time Validation

System checks:

If (Current Time >= Start_Time) AND (Current Time <= End_Time)
      → Access Granted
Else
      → Access Denied


Temperature is displayed continuously during all operations.

🛡️ Admin Mode (Secure Triple-Press Logic)

Admin Mode is not menu-accessible without physical intent.

How Admin Mode Activates:

System is on “Waiting for User ID”

Admin switch pressed 3 times continuously

Enter Admin PIN

Admin Menu appears:

Admin Options

Edit RTC

Edit Time Windows for any user

Exit to main screen

