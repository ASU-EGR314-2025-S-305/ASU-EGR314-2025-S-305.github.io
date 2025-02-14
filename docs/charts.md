
```mermaid
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
    HMI-->>User: Display Robot Path Progress
