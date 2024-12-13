# 🌟 ESP-FC: Multicore & RTOS Integration (Alpha Release) 🌟

🚀 **ESP-FC** is cutting-edge firmware designed for seamless multicore 🌐 and RTOS ⚙️ integration on microcontrollers like ESP32 and RP2040. This is an **alpha release** based on the [GitHub Repository](https://github.com/rtlopez/esp-fc). Below is an overview of its 🧩 capabilities, 🏛️ architecture, and 🌟 practical applications.

---

## 🔍 Overview
This firmware leverages:

- 🧠 **Multicore Support**: Optimized for dual-core processors (e.g., RP2040, ESP32).
- ⏱️ **Real-Time Operating Systems**: Integrates FreeRTOS for task management on ESP32.
- 🕒 **Hardware Timers**: Ensures precision for tasks like gyro updates.
- 📈 **Sensor Fusion Algorithms**: Includes `Madgwick`, `Mahony`, and `Kalman` filters for accurate motion tracking.

### ✨ Key Features
- ✅ Conditional platform-specific compilation.
- 🛠️ Separate task management for critical routines.
- 🧑‍💻 Fallback for single-core microcontrollers.

---

## 🖥️ Code Insights

### ⚙️ Platform-Specific Implementations

#### 🌀 **RP2040 Multicore Configuration**
Efficient task splitting across cores:
```cpp
repeating_timer_t timer;

bool timer_callback(struct repeating_timer *t) {
    espfc.update(true); // Perform the gyro update
    return true;        // Keep the timer running
}

void setup() {
    espfc.load();        // Load configurations
    espfc.begin();       // Initialize the system

    add_repeating_timer_us(-espfc.getGyroInterval(), timer_callback, NULL, &timer);
    multicore_launch_core1(core1_task); // Launch secondary core tasks
}
```

#### ⚡ **ESP32 FreeRTOS Integration**
Dedicated tasks for real-time operations:
```cpp
void gyroTask(void *pvParameters) {
    espfc.begin();
    gyroTimerInit(gyroTimerIsr, espfc.getGyroInterval());
    while (true) {
        ulTaskNotifyTake(pdTRUE, portMAX_DELAY); // Wait for timer notification
        espfc.update(true);
    }
}

void setup() {
    disableCore0WDT(); // Disable Core 0 watchdog
    espfc.load();
    xTaskCreateUniversal(gyroTask, "gyroTask", 8192, NULL, 24, &gyroTaskHandle, 1);
}
```

#### 🧩 **Single-Core Fallback**
For simpler setups:
```cpp
void setup() {
    espfc.load();
    espfc.begin();
}

void loop() {
    espfc.update();
    espfc.updateOther();
}
```

---

## 🌟 Practical Applications
ESP-FC’s architecture makes it ideal for:

- 🛩️ **Drone Flight Controllers**: High-frequency gyro updates and PID tuning.
- 🤖 **Robotics**: Real-time processing for sensor data and motor control.
- 🌐 **IoT Devices**: ESP32’s WiFi support integrates IoT functionalities.

---

## ⚠️ Notes on the Alpha Release
This alpha release is under active development 🛠️ and may contain experimental features. Contributions 📝 and feedback 💡 are welcome through the [GitHub repository](https://github.com/rtlopez/esp-fc).

---

For additional details 📚 or to get started 🚀, visit the [ESP-FC documentation](https://github.com/rtlopez/esp-fc).

---

📂 My GitHub Profile: [BTechIOI](https://github.com/btechioi)
