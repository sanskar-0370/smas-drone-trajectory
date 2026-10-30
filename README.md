# smas-drone-trajectory
Reconstructing a 3D drone trajectory from raw IMU and barometer data without GPS.
## 🚀 Live 3D Visualizer
**[Click here to view the Interactive 3D Flight Visualizer](https://sanskar-0370.github.io/smas-drone-trajectory/)**

## 📖 Project Overview
This project was completed for the **System Modelling, Analysis and Stories (SMAS)** course at IIT Jammu. The objective was to build a complete dead-reckoning navigation pipeline from scratch using a 25-second, 10 Hz flight log containing 3-axis accelerometer, 3-axis gyroscope, and barometric altitude data. 

### Key Methodologies Implemented:
* **Sensor Calibration:** Solved an overdetermined least-squares problem during a stationary ground window (0.0–4.9s) to extract and remove static hardware biases across all 6 IMU channels.
* **Attitude Estimation:** Numerically integrated the Z-axis gyroscope rates to track continuous yaw heading ($\psi$).
* **Frame Transformation:** Utilized a 2D rotation matrix $R_z(\psi)$ to map local body-frame specific forces into the fixed global World frame (East, North, Up).
* **Kinematic Reconstruction:** Removed Earth's gravity ($9.81 m/s^2$) and applied cumulative trapezoidal double-integration in Python to reconstruct 3D velocities and coordinates.
* **Drift Analysis:** Validated the IMU-derived vertical trajectory against independent barometer readings to quantify quadratic double-integration drift.

## 📂 Repository Contents
* `Team08_Drone_Analysis.ipynb`: The core Python pipeline for calibration, integration, and plotting.
* `index.html`: A custom Three.js and TailwindCSS web visualizer that replays the flight telemetry in real-time.
* `Team08_Drone_Report.pdf`: Comprehensive technical report detailing the mathematical models, equations, and error analyses.
* `Team08_Drone_Results.xlsx`: Full 251-step time-series workspace and summary metrics.

## 👥 Team
* Sanskar 
* Shashank Nath
* Ankit Raj
