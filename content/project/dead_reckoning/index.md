---
title: Dead Reckoning
summary: Dead Reckoning using IMU & GPS on an Autonomous Vehicle
date: 2023-10-10
type: docs
math: false
tags:
  - Sensor Fusion

image:
  caption: 'Embed rich media such as videos and LaTeX math'
---

## Project Objective

> The objective of this project was to implement a robust dead reckoning system for an Autonomous Vehicle using Inertial Measurement Unit (IMU) and GPS data. The goal was to estimate the vehicle's position and heading over time in the absence of continuous GPS signals.


[![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?logo=github&style=for-the-badge)](https://github.com/AtharvaJam/dead_reckoning)
---

## Abstract

Dead reckoning provides position estimates by integrating motion data over time, making it crucial in environments where GPS signals are unreliable or unavailable. This project leverages IMU and GPS sensors to estimate vehicle trajectory in such conditions.

A detailed drift analysis was conducted on sensor data fields such as angular velocity, linear acceleration, and magnetic field. Magnetometer calibration was performed using ellipse fitting to correct for hard and soft iron distortions, followed by a complementary filter fusion with gyroscopic data to yield stable yaw estimates.

Forward velocity was computed by integrating the linear acceleration field, with drift and noise corrected using linear regression and second-derivative-based methods. The final dead reckoning estimate was obtained by transforming the velocity into the GNSS frame using real-time yaw values and integrating over time. This estimated trajectory was compared to GPS-based ground truth to evaluate system accuracy.


---

## Results & Analysis

A detailed drift analysis was conducted on raw IMU and magnetometer data. Angular velocity fields exhibited near-zero mean values, confirming expected behavior under static conditions. Linear acceleration fields showed clear offsets and mild Gaussian resemblance, while magnetometer readings revealed strong soft and hard iron distortions due to surrounding ferrous materials. The table below summarizes key statistics and drift estimates (per hour) based on linear regression slopes:

| **Field**                  | **Range**     | **Mean**       | **Std. Dev.** | **Drift/hr** |
|---------------------------|---------------|----------------|---------------|--------------|
| angular_velocity.x        | 0.005924      | -0.000008      | 0.000668      | 0.000120     |
| angular_velocity.y        | 0.008824      | 0.000001       | 0.000946      | -0.000044    |
| angular_velocity.z        | 0.005469      | 0.000003       | 0.000661      | 0.000012     |
| linear_acceleration.x     | 0.103000      | 0.340901       | 0.012759      | -0.002971    |
| linear_acceleration.y     | 0.110000      | 0.514315       | 0.012946      | 0.038681     |
| linear_acceleration.z     | 0.142000      | -9.581304      | 0.016636      | 0.003671     |
| magnetic_field.x          | 0.006700      | -0.044128      | 0.000583      | 0.000871     |
| magnetic_field.y          | 0.102100      | -0.056231      | 0.001725      | 0.000240     |
| magnetic_field.z          | 0.013100      | 0.325593       | 0.002345      | -0.006147    |
| roll                      | 0.002409      | -0.053638      | 0.000585      | -0.003869    |
| pitch                     | 0.001117      | 0.035515       | 0.000151      | -0.000346    |
| yaw                       | 0.011048      | 2.252649       | 0.001668      | 0.006994     |

Yaw estimation was improved through magnetometer calibration using ellipse fitting to correct hard and soft iron distortions. A complementary filter (α = 0.9) was used to blend the magnetometer-based yaw with gyroscope integration, balancing long-term stability with short-term responsiveness. Forward velocity was computed by integrating the linear acceleration (x-axis), followed by drift correction using regression and second-derivative thresholding. These corrections enabled more accurate velocity profiles, especially in stationary segments where the raw IMU data showed spurious motion.

Dead reckoning was performed by transforming the corrected velocity from the vehicle frame to the GNSS frame using yaw data. The resulting trajectory, derived by integrating easting and northing components, was compared with GPS ground truth. Trajectories generated using IMU yaw outperformed those using complementary-filtered yaw during motion, reinforcing the role of angular velocity in dynamic heading estimation. Overall, the fusion of IMU and GPS data produced accurate, drift-compensated trajectories suitable for real-world navigation tasks.


---


## Report

<iframe src="/uploads/projects/dead_reckoning/report.pdf" width="100%" height="600px" style="border: none;">
  This browser does not support PDFs. Please download it: 
</iframe>

[⬇️ Download Full Report (PDF)](/uploads/projects/dead_reckoning/report.pdf)

---
