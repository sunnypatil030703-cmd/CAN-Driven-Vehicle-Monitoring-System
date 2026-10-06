\# 🚗 CAN-Driven Vehicle Monitoring and Driver Assistance System



\### Three-Node LPC2129-Based Vehicle Monitoring and Driver Assistance System Using CAN Communication



A distributed embedded system developed using \*\*LPC2129 microcontrollers\*\* and \*\*CAN communication\*\* for vehicle monitoring, indicator control, fuel monitoring, engine-temperature monitoring, and reverse obstacle detection.



\---



\## 📌 Project Overview



The \*\*CAN-Driven Vehicle Monitoring and Driver Assistance System\*\* is a three-node embedded system designed around the \*\*LPC2129 ARM7 microcontroller\*\*.



The system uses \*\*CAN communication\*\* to exchange vehicle information between independent nodes.



The system consists of:



\- \*\*Main Node\*\*

\- \*\*Fuel Node\*\*

\- \*\*Indicator \& Reverse Alert Node\*\*



The Main Node acts as the central monitoring and display node. It receives information from the other nodes and displays the vehicle status on an LCD.



\---



\## 🎯 Objectives



\- Implement communication between multiple embedded nodes using \*\*CAN protocol\*\*

\- Monitor \*\*fuel level\*\*

\- Monitor \*\*engine temperature\*\*

\- Control \*\*left and right indicators\*\*

\- Detect obstacles during reverse operation

\- Generate \*\*SAFE, WARNING and STOP\*\* alerts

\- Display vehicle information on an LCD

\- Understand and implement \*\*LPC2129 peripherals\*\*

\- Develop modular Embedded C firmware



\---



\# 🏗️ System Architecture



```text

&#x20;                        ┌─────────────────────┐

&#x20;                        │      FUEL NODE      │

&#x20;                        │                     │

&#x20;                        │ LPC2129             │

&#x20;                        │ ADC / Fuel Sensor   │

&#x20;                        └──────────┬──────────┘

&#x20;                                   │

&#x20;                                   │ CAN

&#x20;                                   ▼

┌────────────────────────────────────────────────────────────┐

│                       CAN NETWORK                          │

│                                                            │

│              MCP2551 CAN Transceivers                     │

│                                                            │

└───────────────┬───────────────────────────┬────────────────┘

&#x20;               │                           │

&#x20;               │ CAN                       │ CAN

&#x20;               ▼                           ▼

&#x20;    ┌─────────────────────┐      ┌────────────────────────┐

&#x20;    │     MAIN NODE       │      │ INDICATOR \& REVERSE    │

&#x20;    │                     │      │ ALERT NODE              │

&#x20;    │ LPC2129             │      │ LPC2129                 │

&#x20;    │                     │      │                         │

&#x20;    │ DS18B20             │      │ HC-SR05                 │

&#x20;    │ LCD                 │      │ LEDs                    │

&#x20;    │ Mode Switch         │      │ Buzzer                  │

&#x20;    │ Indicator Switches  │      │ Indicator Control       │

&#x20;    └─────────────────────┘      └────────────────────────┘

