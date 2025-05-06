---
title: Reflection
---

## What we learned
- We learned that it is very difficult to get the ESP32 and PIC to communicate togther.
- Learning how to use micropython proficentally on VScode with the ESP32.
- Really understood how to read other codes.
- Learned how to integrate such subsystems like the mqtt, hmi, motors, and sensors.
- Learned why schematic organiation and PCB layout is important.
- How MQTT works for lightweight wireless communication between subsystems.
- How to simplify user interaction with the HMI subsystem.
- How to use UART communication to reliably send and recieve commands between subsystems.
- Why clear pin management and module planning is when working with microcontrollers like the PIC and ESP32.
- How working in a team enhances problem-solving, especially when integrating different subsystems, code, hardware, and mechanical design.

---

## **Future Recommendations for Students**
- Make sure you define the right pins if you switch the pin layouts.
- Don't try to overcomplicate it with the code.
- Lectures in class are very helpful towards help for any of the subsystems.
- Do not fall behind on making schematics and PCBs, it is a team project.
- Go to office hours whenever needed, and always ask the TAs.
- Always try to checkup on your team just to make sure everyone is up to task.

---

## 📡Communication Architecture – Version 2.0 Reflection

In a **Version 2.0** of our communication architecture, we would focus on improving **reliability, modularity, and scalability** of subsystem communication.

## Potential Future Extensions

Many of the improvements listed below are already present within the group’s systems — including structured message protocols, modular code organization, and debugging support. The following suggestions reflect ways these existing features could be expanded, standardized across all subsystems, or enhanced for greater robustness in future iterations.

### Structured Protocol Format  
The current system uses a consistent message structure (`Start | Sender | Receiver | Data | End`) for UART communication. This improves parsing, enables validation, and simplifies debugging.

**Future extension:**  
Formalize message versioning or message type fields to support a wider range of command formats and features.

---

### Modular Codebase  
Several subsystems separate functionality into clear modules, such as UART parsing, message logic, and application control. This modular approach improves maintainability and scalability.

**Future extension:**  
Standardize this structure across all boards to streamline development, testing, and future integration of new components.

---

### Enhanced Debugging  
Debugging tools — such as verbose logs, debug LEDs, and OLED indicators — are already used to track system behavior and communication states.

**Future extension:**  
Incorporate timestamps, message counters, or structured debug outputs to make logs more informative and consistent.

---

### New Protocol Features  
Message filtering, repeat suppression, invalid message handling, and heartbeat monitoring have already been implemented in parts of the system.

**Future extension:**  
Add ACK/NAK confirmation messages for critical commands, and define more structured error codes for invalid or incomplete messages.

---

### System Reliability  
Timers and lockout mechanisms are in place to avoid repeated stop signals and ensure message handling stability.

**Future extension:**  
Adopt interrupt-based UART reception across all boards and use buffering or queuing strategies to improve responsiveness during high traffic.

---

### Peripheral Expansion  
I2C communication is already implemented for the color sensor subsystem.

**Future extension:**  
Expand support for other sensors (e.g., SPI-based), and consider structured handlers for interpreting more complex sensor data.

---

## Why These Changes?

These improvements would make the system more robust for future classroom projects, easier to debug and extend, and better suited for integration with additional subsystems such as distance sensing, autonomous navigation, or remote control modules.


