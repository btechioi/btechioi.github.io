# 🚀 Project -> ESP-FC: Multicore & RTOS Integration (Alpha Release)

---

## 🌐 GitHub Repository  
Find the source code and documentation on [GitHub](https://github.com/rtlopez/esp-fc).  
Also, check out my GitHub profile: [BTechIOI](https://github.com/btechioi).
yea 

---

## 🧾 Project Description  
- ESP-FC is an advanced firmware designed for seamless multicore and RTOS integration on microcontrollers like ESP32 and RP2040. The project includes:
  - **Conditional Compilation**: Platform-specific optimizations for ESP32, RP2040, and single-core setups.
  - **Real-Time Operating Systems**: FreeRTOS integration for efficient task management.
  - **Sensor Fusion Algorithms**: Kalman, Madgwick, and Mahony filters for accurate motion tracking.
  - **Hardware Timer Usage**: Precise execution of critical routines such as gyro updates.

---

## 📢 Project Information  
Created:: 13-12-2024 {{time}}  
Deadline::  
Hibernating::  
Completion date expected::  
Completed::  
Type:: Firmware Development & Embedded Systems  
Tags:: ESP32, RP2040, RTOS, Multicore, Sensor Fusion  
Platform:: Arduino, FreeRTOS  

---

## 🎯 Objective

1. 🟢 **Ideal project result**  
    - A fully functional multicore and RTOS-integrated firmware for ESP32 and RP2040, supporting real-time task management and sensor fusion.  
2. 🟠 **Acceptable result**  
    - A single-core firmware fallback with basic real-time task execution.

---

## ❓ Expectations

1. 🟢 **Helpful to the project**  
    - Efficient use of multicore capabilities.  
    - Smooth integration of FreeRTOS for real-time task management.  
2. 🟠 **Roadblocks**  
    - Debugging FreeRTOS-specific tasks and timer ISR implementations.  
    - Ensuring accurate sensor fusion despite environmental noise.  
3. 👶 **Naivety**  
    - Assuming hardware timers work identically across platforms without adaptation.  
4. 👨‍💻 **Insights**  
    - Modular architecture simplifies debugging and future enhancements.  

---

## ✅ Tasks  
- Implement FreeRTOS-based gyro and PID update tasks for ESP32.  
- Validate multicore task splitting on RP2040 using `multicore_launch_core1`.  
- Develop fallback support for single-core systems.  
- Test sensor fusion algorithms under real-world conditions.  

---

## 📦 Resources  
- ESP32 and RP2040 microcontrollers.  
- Libraries: FreeRTOS, Madgwick, Mahony, Kalman filters.  
- Development tools: Arduino IDE, PlatformIO.  

---

## 📂 Project Logs  
- Initial configuration for ESP32 completed with FreeRTOS task creation.  
- Multicore implementation for RP2040 validated using hardware timers.  
- Single-core fallback tested successfully with simulated tasks.  
- Sensor fusion accuracy evaluation pending real-world testing.  

