---
title: Control Barrier Functions
summary: Investigating Control Barrier Functions for mult-agent safety
date: 2025-05-24
type: docs
math: false
tags:
  - Swarm Robotics
  - Safety-critical systems
image:
  caption: 'Embed rich media such as videos and LaTeX math'
---

## Project Objective

> To investigate and implement novel formulations of Control Barrier Functions (CBFs) for multi-robot collision avoidance, focusing on methods that are both optimal and distributed in nature. The goal is to improve safety guarantees and scalability in decentralized robotic systems.

#### Research Supervisor

[Yasin Yazicioglu](https://www.linkedin.com/in/yasin-yaz%C4%B1c%C4%B1o%C4%9Flu-2a6475203/)


Gazebo Codebase: [![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?logo=github&style=for-the-badge)](github.com/AtharvaJam/Control-Barrier-Gazebo)


Python Codebase: [![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?logo=github&style=for-the-badge)](github.com/AtharvaJam/control_barrier_functions_py_sim)

---

## Abstract



This project explores novel Control Barrier Function (CBF) formulations for multi-robot collision avoidance, focusing on scalability and smooth control under distributed settings. We implement two approaches: an optimal distributed CBF that allows robots to compute locally safe controls with minimal coordination, and a log-sum-exp relaxation that replaces the non-smooth minimum operator in safety constraints, resulting in better optimization performance.

The methods are evaluated in a Python-based simulator using second-order (double integrator) robot dynamics, with comparisons to a centralized CBF baseline. Key metrics include collision avoidance, control smoothness, and constraint satisfaction. To validate real-world applicability, the controllers are deployed in a Gazebo + ROS1 Noetic environment with TurtleBot3 agents operating in shared spaces. Compared to the baseline, our methods show improved safety and smoother trajectories, particularly in high-density scenarios.

---
