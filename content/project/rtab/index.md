---
title: RTAB SLAM
summary: RTAB SLAM for indoor environments
date: 2023-12-24
type: docs
math: false
tags:
  - Robot Sensing & Navigation
image:
  caption: 'Embed rich media such as videos and LaTeX math'
---

## Project Objective

> The objective of this project was to implement and evaluate the performance of the RTAB-Map SLAM algorithm in both controlled indoor and dynamic outdoor environments. The system aimed to generate accurate 2D and 3D maps using RGB-D, stereo, and LiDAR sensors by leveraging visual odometry, loop closure, and graph-based optimization techniques. 


#### Contributors

1. [Febin Wilson](https://www.linkedin.com/in/febinwil/)

2. [Anusha Manohar](https://www.linkedin.com/in/anusham2022/)

3. [Ruchik Jani](https://www.linkedin.com/in/ruchik-jani-b55a7a152/)

[![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?logo=github&style=for-the-badge)](https://github.com/AtharvaJam/Monocular-RTAB)

---

## Abstract

RTAB-Map (Real-Time Appearance-Based Mapping) is a graph-based SLAM algorithm that combines visual odometry, loop closure detection, and memory management to enable real-time mapping in large-scale environments. In this project, RTAB-Map was deployed across three datasets: a structured indoor developer dataset, an outdoor dataset from the NUANCE autonomous vehicle on Newbury Street, and an indoor dataset captured using an iPhone at Northeastern University’s Snell Library.

The front-end of RTAB-Map extracts SURF features and employs a bag-of-words approach for image comparison and loop closure hypothesis. The back-end integrates these constraints into a factor graph, optimized using GTSAM or g2o, for pose estimation. The project utilized RGB-D cameras, stereo cameras, LiDAR, and IMU data to build dense 3D point clouds, occupancy grids, and 2D projection maps. The loop closure and memory strategies (STM, WM, and LTM) were tuned for real-time processing. Challenges encountered included low-light conditions, feature-poor areas, and dynamic scenes in the outdoor dataset.


---

<!-- 
## Demo Video

{{< youtube LCxA5zYdCbA >}}

--- -->

## Results & Analysis


RTAB-Map performed exceptionally well on the **indoor developer dataset**, generating complete 3D and 2D occupancy maps with reliable loop closure detections. Feature-rich scenes and deliberate panning movements helped achieve accurate global mapping. In the **NEU indoor dataset**, mapping was successful with sufficient loop closures, though false-positive occupancy grid cells appeared in empty regions due to sensor noise. The system effectively leveraged LiDAR and iPhone camera fusion, even in low-texture regions.

However, performance **degraded significantly in the NEU outdoor dataset**. The stereo camera struggled in poorly-lit, low-feature urban scenes, causing odometry failures (marked by red overlays). The system failed to produce a 3D map and did not detect valid loop closures. Challenges included fast camera movement, poor depth resolution from stereo baseline constraints, and moving obstacles (pedestrians, cyclists). The comparison underscores that RTAB-SLAM is highly effective in static, structured, and well-lit indoor environments, but requires tuning or alternative sensor modalities to handle unstructured, dynamic outdoor conditions.

---


## Report

<iframe src="/uploads/projects/rtab/report.pdf" width="100%" height="600px" style="border: none;">
  This browser does not support PDFs. Please download it: 
</iframe>

[⬇️ Download Full Report (PDF)](/uploads/projects/rtab/report.pdf)

---

## Presentation

<iframe src="/uploads/projects/rtab/presentation.pdf" width="100%" height="600px" style="border: none;">
  This browser does not support PDFs. Please download it: 
</iframe>

[⬇️ Download Full Presentation (PDF)](/uploads/projects/rtab/presentation.pdf)

---
