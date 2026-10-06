# Bike Rear-Vehicle Detector

An experimental prototype using a Raspberry Pi 5 and a single camera to detect, track, and estimate the distance/closing speed of vehicles approaching from behind, providing a real-time handlebar LED alert.

> **Disclaimer:** This is an experimental engineering prototype, not a certified safety device. 

---

## System Architecture
* **Hardware:** Raspberry Pi 5, Pi Camera Module, Handlebar LED, Power Bank.
* **Mounting:** Custom 3D-printed SolidWorks mount with fixed height and tilt.
* **Software Stack:** Python, OpenCV, NumPy, Pandas, Linux (Bash), C++.

---

## Project Scope & Metrics
The project is evaluated on measured performance rather than qualitative claims:
* **Detection Range:** Maximum distance vehicles are reliably detected.
* **Distance Error:** Difference between estimated vs. actual ground-truth distance.
* **Alert Latency:** Delay between vehicle approach and LED trigger.
* **False Alerts:** Number of false triggers per ride hour across varied conditions.
* **Compute Performance:** Real-time processing speed (Target: 5+ FPS on Pi 5).

---

## Repository Structure
├── src/         # Python & C++ source code (detection, tracking, alert logic)
├── cad/         # SolidWorks CAD files (.sldprt, .sldasm) & 3D prints (.stl)
├── docs/        # Written notes, weekly logs, and requirements spec
└── assets/      # CAD renders, circuit diagrams, and prototype photos
