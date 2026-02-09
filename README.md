AI/ML-based patient health monitoring system using Raspberry Pi that tracks BPM, SpO₂, temperature, and ECG in real time, predicts health risk locally, and triggers visual and audible alerts.


# AI/ML Based Patient Health Monitoring and Alerting Robot

## 1. Problem Statement

Traditional health monitoring systems are largely hospital-centric, expensive, and unsuitable for continuous long-term monitoring in home or remote environments. Many low-cost solutions monitor only a single parameter and lack intelligent health risk prediction.

This project addresses these gaps by delivering a **low-cost, real-time, AI/ML-enabled patient health monitoring system** capable of local decision-making and immediate alerting without cloud dependency.

---

## 2. Solution Overview

A **Raspberry Pi–based edge computing system** that continuously monitors multiple physiological parameters, applies machine learning for health risk classification, and triggers visual and audible alerts during abnormal conditions.

Key design focus:

* Real-time operation
* Local ML inference (edge AI)
* Multi-sensor integration
* Long-duration headless deployment

---

## 3. Core Features

* Continuous monitoring of:

  * Heart Rate (BPM)
  * Blood Oxygen Saturation (SpO₂)
  * Body Temperature (non-contact)
  * ECG waveform
* Edge-based machine learning health risk prediction
* Health classification:

  * Normal
  * Abnormal
  * Critical
* Real-time alerts using:

  * RGB LED indicators
  * Active buzzer
* Dual OLED display system for clear visualization
* CSV dataset generation for ML training
* Optional mobile application for remote monitoring

---

## 4. System Architecture

* **Sensing Layer**

  * MAX30102 (BPM, SpO₂)
  * MLX90614 (Temperature)
  * AD8232 + MCP3008 (ECG)

* **Processing Layer**

  * Raspberry Pi 4
  * Signal preprocessing
  * Feature extraction
  * ML inference

* **Application Layer**

  * OLED displays
  * Alert system
  * Mobile app (optional)

All computation is performed locally (edge computing).

---

## 5. Hardware Stack

* Raspberry Pi 4 Model B
* MAX30102 Pulse Oximeter
* MLX90614 Infrared Temperature Sensor
* AD8232 ECG Sensor
* MCP3008 ADC
* 0.96” OLED (Vitals + ECG)
* 1.3” OLED (Status + Risk)
* RGB LED
* Active Buzzer

---

## 6. Software & Tools

**Programming & Development**

* Python 3
* Thonny IDE
* Visual Studio Code

**Libraries**

* Sensor & hardware: `smbus2`, `gpiozero`, `busio`, `digitalio`
* Displays: `adafruit_ssd1306`, `luma.oled`
* Data & ML: `numpy`, `pandas`, `scikit-learn`

---

## 7. Machine Learning Module

* Algorithm: Random Forest Classifier
* Input Features:

  * Heart rate metrics
  * SpO₂ statistics
  * Temperature values
  * ECG voltage features
* Output Classes:

  * Normal
  * Abnormal
  * Critical
* Training:

  * Dataset generated directly from real sensor data
  * Offline training
  * Real-time inference using saved model

---

## 8. Alert Logic

* Normal:

  * Blue LED
* Abnormal:

  * Green LED
  * Intermittent buzzer
* Critical:

  * Red LED
  * Continuous buzzer

---

## 9. Testing & Results

* Stable real-time monitoring achieved
* Accurate alert triggering under abnormal conditions
* Successful long-duration headless operation
* Sensor accuracy:

  * Temperature: ~95–100%
  * ECG waveform stability: ~95–99%
  * BPM & SpO₂: ~85–90%

---

## 10. Repository Structure

```
health-monitoring-robot/
│
├── hardware/
│   ├── circuit_diagram.pdf
│   ├── block_diagram.png
│   └── pin_configuration.md
│
├── src/
│   ├── health.py                 # Main system code
│   ├── sensors/
│   │   ├── max30102.py
│   │   ├── mlx90614.py
│   │   └── ecg_ad8232.py
│   ├── display/
│   │   ├── oled_vitals.py
│   │   └── oled_status.py
│   └── alerts/
│       ├── led_control.py
│       └── buzzer.py
│
├── ml/
│   ├── dataset/
│   │   └── health_data.csv
│   ├── train_model.py
│   └── model.pkl
│
├── mobile_app/
│   └── flutter_app/
│
├── docs/
│   ├── project_report.pdf
│   └── presentation.pptx
│
├── requirements.txt
├── README.md
└── LICENSE
```

---

## 11. Impact & Use Cases

* Home healthcare monitoring
* Elderly care systems
* Remote patient monitoring
* Emergency alert systems
* Academic and research applications

---

## 12. Limitations

* Not medically certified
* Sensor accuracy depends on placement and environment
* ML accuracy depends on dataset size

---

## 13. Future Scope

* Deep learning for ECG analysis
* Cloud and telemedicine integration
* Wearable form factor
* Doctor notification system
* Multi-patient monitoring dashboard
