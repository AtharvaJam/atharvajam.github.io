---
title: Leo Explore
summary: Search & Explore motion planning package mobile 
date: 2024-04-10
type: docs
math: false
tags:
  - Mobile Robotics
  - Motion Planning
image:
  caption: 'Embed rich media such as videos and LaTeX math'
---

## Project Objective

> The objective of this project was to design and implement an autonomous reconnaissance robot capable of exploring unknown environments using a modular and intelligent navigation system. The robot is designed to operate in both simulated and real-world environments, with applications ranging from disaster response to military reconnaissance.

#### Contributors

1. [Bhanu Prasad A J](https://www.linkedin.com/in/bhanuprasadaj/)

2. [Abhishek Uddaraju](https://github.com/U-Abhishek)

3. [Yijian Huang](https://www.linkedin.com/in/yijianhuang/)

4. [Tim Wu](https://www.linkedin.com/in/jiatong-wu/)


[![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?logo=github&style=for-the-badge)](https://github.com/AtharvaJam/Leo_explore)

---


## Abstract


This project introduces the **Reconnaissance Bot**, a robotic system built to navigate and explore uncharted environments with minimal human intervention. The bot uses a top-down control architecture composed of three key components:

The **Frontier Server** identifies potential exploration goals using a K-Means clustering algorithm to process frontier points. The **Global Planner** employs the A* algorithm to compute an optimal path from the robot’s current location to the selected goal. The **Local Planner** implements a Model Predictive Path Integral (MPPI) control method to generate smooth, collision-free trajectories within the robot’s immediate environment.

The system integrates seamlessly with ROS-based SLAM for localization and mapping, allowing a clean separation of responsibilities between mapping and planning modules. This decoupled architecture ensures modularity, extensibility, and robust real-time performance. The Reconnaissance Bot was evaluated through extensive simulation using Gazebo and real-world testing on the Northeastern University campus.


---


## Demo Video

{{< youtube fyIsYrZ6wks >}}

---
## Results & Analysis

### Simulation Testing

Two Gazebo simulation environments were used to evaluate system performance:

1. **TurtleBot3 House** — A hexagon-shaped grid map resembling a turtle.
2. **TurtleBot3 World** — A more realistic, house-like indoor setup.

The primary metric used to assess performance was the **Rate of Exploration**, defined as the ratio of explored area to time taken (m²/s). The simulation revealed that the exploration rate decreases non-linearly as the environment size increases, following an inverse proportionality to the 1.5th power of the area.

| Environment          | Area Explored (m²) | Time Taken (s) | Rate of Exploration (m²/s) |
|----------------------|--------------------|----------------|-----------------------------|
| TurtleBot3 House     | 21.88               | 74s           | 0.30              |
| TurtleBot3 World     | 83.82               | 560s           | 0.15             |


### Real-World Testing

The system was deployed in two real-world environments at Northeastern University:

1. **4x4 Maze World**
2. **Hurtig Hall Corridor**

The local planner, operating at 12 Hz, successfully generated agile, real-time trajectories using MPPI. Perturbation-based trajectory sampling enabled smooth obstacle avoidance, while velocity control (0.8 m/s nominal, angular range [0, π] rad/s) facilitated natural movement. Demonstration videos captured during testing validated the planner’s effectiveness in real-world conditions, closely matching the simulation results.

Overall, the Reconnaissance Bot consistently performed seamless exploration and robust navigation across a variety of structured environments, with modular code and scalable planning strategies providing a strong foundation for future enhancements.

---


## Report

<iframe src="/uploads/projects/leo_explore/report.pdf" width="100%" height="600px" style="border: none;">
  This browser does not support PDFs. Please download it: 
</iframe>

[⬇️ Download Full Report (PDF)](/uploads/projects/leo_explore/report.pdf)

---

## Presentation

<iframe src="/uploads/projects/leo_explore/presentation.pdf" width="100%" height="600px" style="border: none;">
  This browser does not support PDFs. Please download it: 
</iframe>

[⬇️ Download Full Presentation (PDF)](/uploads/projects/leo_explore/presentation.pdf)

---
