---
title: Reflection
---

## 📝What we learned
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

## **Future Recommendations for Students**
- Make sure you define the right pins if you switch the pin layouts.
- Don't try to overcomplicate it with the code.
- Lectures in class are very helpful towards help for any of the subsystems.
- Do not fall behind on making schematics and PCBs, it is a team project.
- Go to office hours whenever needed, and always ask the TAs.
- Always try to checkup on your team just to make sure everyone is up to task.

## 📡Communication Architecture – Version 2.0 Reflection

In a **Version 2.0** of our communication architecture, we would focus on improving **reliability, modularity, and scalability** of subsystem communication.

### 🛠️Improvements

- **Structured Protocol Format**  
  Use a consistent message structure like:  
  `Start Byte | Sender | Receiver | Data | End Byte`  
  This improves parsing, enables validation, and simplifies debugging.

- **Modular Codebase**  
  Split the communication logic into:
  - `comm_uart.py`: UART receive/parse functions
  - `comm_logic.py`: High-level command handling
  - `main.py`: Application loop  
  This makes it easier to test, maintain, and expand the codebase.

- **Enhanced Debugging**  
  - Add verbose logs over UART or OLED (`"MSG RECEIVED"`, `"UNKNOWN CMD"`, etc.)
  - Use debug LEDs to indicate message status or errors
  - Include timestamps or counters in messages for tracking

- **New Protocol Features**  
  - ACK/NAK support for command confirmation
  - Ping/heartbeat messages to verify active links
  - Error codes for invalid or incomplete messages

- **System Reliability**  
  - Implement watchdog timers to recover from software crashes
  - Use interrupt-based UART for consistent message reception
  - Add message queues or buffers to handle burst traffic

- **Peripheral Expansion**  
  - Add I2C or SPI sensors with structured message handlers
  - Explore JSON-style messaging for human-readability if memory allows

### 📈 Why These Changes?

These improvements would make the system more robust for classroom use, easier to debug and extend, and better suited to interact with additional components like distance sensors, displays, or future subsystems.


