---
layout: single
title: "Research"
permalink: /research/
---

## 🔬 Current Research

### <a id="arcas"></a>ARCAS: Augmented Reality Collision Avoidance System
[Mobile Automation and Sensing Systems (MASS) Lab](https://www.mass-lab-ut.com/) | The University of Texas at Austin  
📆 Jan. 2025 - Present  

<hr style="border: none; border-top: 1px dashed #aaa; margin: 1.2em 0;">

<div style="display: flex; justify-content: center; gap: 12px; flex-wrap: wrap;">
  <figure style="text-align:center; width:45%;">
    <img src="/assets/images/research_arcas_main.png" alt="ARCAS concept" style="width:100%; border-radius:8px;">
    <figcaption>ARCAS Concept Diagram</figcaption>
  </figure>
</div>

  **Summary:** A real-time AR system that integrates 2D LiDAR sensing with wearable interfaces to enhance spatial awareness and prevent collisions between pedestrians and vehicles.  
  **Keywords:** Traffic Safety, Real-Time Sensing, Augmented Reality, Human–Vehicle Interaction  
  **Hardware:** Meta Quest Pro, RPLiDAR C1, MicroStrain by HBK 6287-9960 IMU, Logitech Brio 501 Webcam, Server Laptop  
  **Software:** Unity (C#), C++, Python  

<hr style="border: none; border-top: 1px dashed #aaa; margin: 1.2em 0;">

  **Background:**  
  Global road traffic injuries remain one of the leading causes of death, with over 1.3 million fatalities each year (WHO, 2022). In particular, collisions between vehicles and vulnerable road users (VRUs) — such as pedestrians and cyclists — have increased with rising urban density (GHSA, 2024). Although autonomous and connected vehicles are being developed to enhance traffic safety, they often fail to communicate their intentions clearly to surrounding humans, which leads to trust and predictability issues in shared environments (Habibovic et al., 2018; Dey et al., 2020).  
  
  **Problem:**   
  Most existing external Human–Machine Interfaces (eHMI) focus on vehicle-to-pedestrian communication using displays or projections mounted on the vehicle body. However, these interfaces lack scalability, environmental awareness, and real-time adaptability, especially in dynamic or obstructed urban scenes (Carmona et al., 2021; Colley et al., 2020). As a result, pedestrians outside the direct line of sight or those distracted cannot receive timely safety cues.  

<div style="display: flex; justify-content: center; gap: 12px; flex-wrap: wrap;">
  <figure style="text-align:center; width:45%;">
    <img src="/assets/images/research_arcas_lidar_system_layout_workflow.png" alt="ARCAS concept" style="width:100%; border-radius:8px;">
    <figcaption>System layout and visualization workflow.</figcaption>
  </figure>
</div>
  
  **Methodology: Overview**   
  To address this, ARCAS introduces a wearable Augmented Reality system that integrates 2D LiDAR sensors and AR headsets (Meta Quest Pro) for real-time environment perception and visualization. The roadside LiDAR detects surrounding vehicles and pedestrians, while the server PC processes point clouds, performs object tracking, and transmits positional data to the headset.  

  In the headset, a custom Unity (C#) client overlays 3D bounding boxes, positional markers, and motion cues in the user’s field of view, effectively extending situational awareness beyond the physical line of sight. The data synchronization between LiDAR and headset is handled through a Python-based TCP communication module, ensuring low-latency, frame-aligned visualization.  

  **Methodology: Detail**  

<div style="border:1px solid #ddd; background:#fafafa; padding:14px 16px; border-radius:10px; margin:12px 0;">
  <strong>ARCAS Development Phases</strong><br>
  (1) <b>AR Headset–LiDAR Integration</b><br>
  Single-user prototype linking real-time LiDAR sensing with AR visualization.<br>
  📆 Jan. 2025 - Apr. 2025<br>
  (2) <b>Multi-User Shared Perception</b><br>
  Synchronizing spatial awareness across multiple AR headsets in a shared scene.<br>
  📆 May 2025 - Aug. 2025<br>
  (3) <b>In-Vehicle AR User</b><br>
  Extending collision visualization to drivers inside vehicles for cross-scenario awareness.<br>
  📆 Sept. 2025 - Current
</div>  
  
  **Results:**  

### <a id="hrc"></a>Augmented Mobile Robots with Shared Perception in Uncertain Environments
An AR-assisted human–robot collaboration system that enables shared perception and intent understanding in uncertain environments.

