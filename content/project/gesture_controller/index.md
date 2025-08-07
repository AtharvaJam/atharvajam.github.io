---
title: Gesture-based Teleop
summary: A webcam feed-based gesture controller for the Stretch Robot
date: 2025-04-20
type: docs
math: false
tags:
  - Computer Vision
image:
  caption: 'Gesture-based Teleop'
---

## Project Objective

> To develop a modular, real-time gesture recognition system for intuitive teleoperation of the Stretch robot, enabling users to control the robot's base, arm, and gripper using only natural hand and arm gestures captured via a standard webcam. The goal is to improve human–robot interaction (HRI) by eliminating the need for wearable devices or complex hardware setups.

#### Contributors

1. [Shubhankar Katekari](https://www.linkedin.com/in/shubhankar-katekari-157705218/)

2. [Nikhil Chowdary Gutlapalli](https://www.linkedin.com/in/gutlapalli-nikhil-chowdary/)

[![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?logo=github&style=for-the-badge)](https://github.com/AtharvaJam/gesture-based-teleop)


---

## Abstract

This project presents a markerless, real-time gesture-based control framework for teleoperating the Stretch robot using off-the-shelf hardware and open-source software. Leveraging Mediapipe for hand and pose landmark detection and ROS2 for communication and control, the system translates human gestures captured via webcam into commands for the robot’s base, arm, and gripper.

The architecture consists of two ROS2 nodes: a Menu Node for managing interaction modes and a Controller Node that maps gestures to robot-specific kinematics. Different gesture sets are used to control different functionalities (e.g., palm direction for base movement, finger positions for gripper control), offering intuitive transitions between modes. A “two open palms” gesture halts gesture processing and resets the system to an idle state, enhancing user control flow.

Designed with modularity and accessibility in mind, the system runs on standard consumer hardware and requires no calibration or wearable devices. It offers a practical foundation for natural HRI in assistive robotics, research labs, or remote operation scenarios.

---


## Demo Video

{{< youtube LCxA5zYdCbA >}}

---

## Results & Analysis


To evaluate system performance, we deployed the gesture recognition framework on the Stretch 3 robot model within the Ignition Gazebo simulator, using ROS2 Humble. All testing was conducted on a standard mid-range PC simulating a 30 FPS webcam input. A user study involving 5 participants was conducted, each performing five predefined gesture types: Base Movement, Arm Up/Down, Arm Stretch/Retract, Gripper Open/Close, and Two Palm (Idle/Quit).

Across 100 gesture instances per category, we measured accuracy, recall, average latency, and false positive rates.
| Gesture Type            | Accuracy | Recall | Latency (s) | False Positives |
|------------------------ |--------- |------- |------------ |----------------|
| Base Movement           | 0.95     | 0.93   | 0.20        | 0.05           |
| Arm Up/Down             | 0.90     | 0.88   | 0.22        | 0.07           |
| Arm Stretch/Retract     | 0.88     | 0.85   | 0.25        | 0.09           |
| Gripper (Open/Close)    | 0.96     | 0.94   | 0.19        | 0.04           |
| Two Palms (Quit Signal) | 0.85     | 0.90   | 0.29        | 0.15           |

User Feedback: Participants reported that the system was easy to learn and appreciated the hover-based menu interface, especially its forgiving 2-second selection window. Some suggested improving responsiveness of the "two palms" gesture, though this would require balancing sensitivity against false positives. Overall, the gesture system was perceived as intuitive and effective, supporting our goal of a modular, natural HRI interface.

---


## Report

<iframe src="/uploads/projects/gesture_controller/report.pdf" width="100%" height="600px" style="border: none;">
  This browser does not support PDFs. Please download it: 
</iframe>

[⬇️ Download Full Report (PDF)](/uploads/projects/gesture_controller/report.pdf)

---

## Presentation

<iframe src="/uploads/projects/gesture_controller/presentation.pdf" width="100%" height="600px" style="border: none;">
  This browser does not support PDFs. Please download it: 
</iframe>

[⬇️ Download Full Presentation (PDF)](/uploads/projects/gesture_controller/presentation.pdf)

---
