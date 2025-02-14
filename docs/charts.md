## Sequence Diagram (Process Flow)
This sequence diagram illustrates how messages and commands flow between the user, microcontroller, sensors, actuators, and HMI display in our line-following robot system.  

### **How the Line-Following Robot Works:**
- The User starts the robot using the HMI subsystem.
   
- The ESP32 microcontroller receives the command from the HMI and begins processing sensor data.
  
- The Color Sensor Subsystem detects the path line and communicates this data to the ESP32 using I2C communication.
   
- The ESP32 processes the sensor data and determines the required motor adjustments to keep the robot on track.
   
- The Motor Driver Subsystem receives speed and direction commands from the ESP32 and adjusts the motor movement accordingly using PWM signals.
  
- The Motor Driver also sends status feedback back to the ESP32 to ensure real-time adjustments.
    
- The HMI  receives updated robot status from the ESP32 and displays the information for the user.
  
- The process repeats continuously, ensuring that the robot follows the line smoothly.  

### **Communication Protocols Used:**
- I2C Communication → Used between the ESP32 and the Color Sensor for data exchange.
  
- PWM Signals → Used between the ESP32 and the Motor Driver to control motor speed and direction.
  
- UART Communication → Used for debugging and potential remote monitoring.  

``` mermaid
sequenceDiagram
    autonumber
    participant User
    participant HMI as Agilan (HMI - OLED Display)
    participant Zack as Zack (ESP32 - Main Controller)
    participant David as David (Color Sensor Subsystem - I2C)
    participant Andrew as Andrew (Motor Driver Subsystem - PWM)

    User->>HMI: Start Line-Following Mode
    HMI->>Zack: Activate Line-Following Algorithm
    Zack->>David: Request Line Color Data (I2C)
    David-->>Zack: Send Color Data (I2C)
    Zack->>Andrew: Adjust Speed and Direction (PWM)
    Andrew-->>Zack: Send Motor Status Feedback
    Zack-->>HMI: Update Robot Status
    HMI-->>User: Display Robot Path Progress
