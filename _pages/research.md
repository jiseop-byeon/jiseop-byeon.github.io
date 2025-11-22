---
layout: single
title: "Research"
author_profile: true
toc: true
toc_sticky: true
permalink: /research/
---

## 🔬 Current Research

### <a id="arcas"></a>· ARCAS: Augmented Reality Collision Avoidance System
[Mobile Automation and Sensing Systems (MASS) Lab](https://www.mass-lab-ut.com/) | The University of Texas at Austin  
📆 Jan. 2025 - Present  

<hr style="border: none; border-top: 1px dashed #aaa; margin: 1.2em 0;">

**Publication:**   

<div style="display: flex; justify-content: center; gap: 12px; flex-wrap: wrap;">
  <figure style="text-align:center; width:60%;">
    <img src="/assets/images/research_arcas_main.png" alt="ARCAS concept" style="width:100%; border-radius:8px;">
    <figcaption>ARCAS Concept Diagram</figcaption>
  </figure>
</div>

  **Summary:** ARCAS is a real-time augmented reality (AR) system that integrates 3D LiDAR sensing with wearable headsets to enhance spatial awareness and prevent collisions between pedestrians and vehicles. The system operates through TCP/IP communication between a LiDAR processing server and AR headsets, detecting nearby objects and visualizing potential collision risks directly in the user’s field of view. It evolves from a single-user setup linking LiDAR perception with AR visualization to a coordinated framework that synchronizes multiple headsets and extends situational awareness to vehicle occupants. As a human-in-the-loop system, ARCAS allows users to perceive, anticipate, and respond to dynamic traffic hazards, bridging human perception and automated sensing for safer mixed traffic environments.  
  
  **Keywords:** Traffic Safety, Real-Time Sensing, Augmented Reality, Human–Vehicle Interaction  
  
  **Tools:**  
  &nbsp;&nbsp;• **Hardware:** Meta Quest Pro, Velodyne VLP-16 LiDAR, MicroStrain by HBK 6287-9960 IMU, Logitech Brio 501 Webcam, Server Laptop  
  &nbsp;&nbsp;• **Software:** Unity (C#), C++, Python

<hr style="border: none; border-top: 1px dashed #aaa; margin: 1.2em 0;">

  **Background:**  
  Global road traffic injuries remain one of the leading causes of death, with over 1.3 million fatalities each year [1]. In particular, collisions between vehicles and vulnerable road users (VRUs) — such as pedestrians and cyclists — have increased with rising urban density [2]. Although autonomous and connected vehicles are being developed to enhance traffic safety, they often fail to communicate their intentions clearly to surrounding humans, which leads to trust and predictability issues in shared environments [3], [4].
  
  **Problem:**   
  Most existing external Human–Machine Interfaces (eHMI) focus on vehicle-to-pedestrian communication using displays or projections mounted on the vehicle body. However, these interfaces lack scalability, environmental awareness, and real-time adaptability, especially in dynamic or obstructed urban scenes (Carmona et al., 2021; Colley et al., 2020). As a result, pedestrians outside the direct line of sight or those distracted cannot receive timely safety cues.  

<div style="display: flex; justify-content: center; gap: 12px; flex-wrap: wrap;">
  <figure style="text-align:center; width:60%;">
    <img src="/assets/images/research_arcas_lidar_system_layout_workflow.png" alt="ARCAS concept" style="width:100%; border-radius:8px;">
    <figcaption>System layout and visualization workflow.</figcaption>
  </figure>
</div>
  
  **Methodology: Overview**   
  To address this, ARCAS introduces a wearable Augmented Reality system that integrates 3D LiDAR sensors and AR headsets (Meta Quest Pro) for real-time environment perception and visualization. The roadside LiDAR detects surrounding vehicles and pedestrians, while the server PC processes point clouds, performs object tracking, and transmits positional data to the headset.  

  In the headset, a custom Unity (C#) client overlays 3D bounding boxes, positional markers, and motion cues in the user’s field of view, effectively extending situational awareness beyond the physical line of sight. The data synchronization between LiDAR and headset is handled through a Python-based TCP communication module, ensuring low-latency, frame-aligned visualization.  

  **Methodology: Detail**  

<div style="border:1px solid #ddd; background:#fafafa; padding:14px 16px; border-radius:10px; margin:12px 0;">
  <strong>ARCAS Development Phases</strong>
  <h4 id="arcas-phase1" style="margin:0;">
    <a href="/arcas_phase1/" style="text-decoration:none;">(1) AR Headset–LiDAR Integration →</a>
  </h4>
  Single-user prototype linking real-time LiDAR sensing with AR visualization.<br>📆 Jan. 2025 - Apr. 2025
  <h4 id="arcas-phase2" style="margin:0;">
    <a href="/arcas_phase2/" style="text-decoration:none;">(2) Multi-User Shared Perception →</a>
  </h4>
  Synchronizing spatial awareness across multiple AR headsets in a shared scene.<br>📆 May 2025 - Aug. 2025
  <h4 id="arcas-phase3" style="margin:0;">
    <a href="/arcas_phase3/" style="text-decoration:none;">(3) In-Vehicle AR User →</a>
  </h4>
  Extending collision visualization to drivers inside vehicles for cross-scenario awareness.<br>📆 Sept. 2025 - Present
</div>
  
  **Results:**  

  **Reference:**  
  [1] World Health Organization, *Global Status Report on Road Safety 2023*, Geneva, Switzerland: WHO, 2023. [Online].  
  Available: [https://www.who.int/news-room/fact-sheets/detail/road-traffic-injuries](https://www.who.int/news-room/fact-sheets/detail/road-traffic-injuries)  
  Accessed: Nov. 7, 2025.
  
  [2] Governors Highway Safety Association (GHSA), *U.S. Pedestrian Deaths Fall Slightly in First Half of 2023, but Remain Above Pre-Pandemic Levels*, 2024. [Online].  
  Available: [https://www.ghsa.org/news/us-pedestrian-deaths-fall-slightly-first-half-2023-remain-above-pre-pandemic-levels](https://www.ghsa.org/news/us-pedestrian-deaths-fall-slightly-first-half-2023-remain-above-pre-pandemic-levels)  
  Accessed: Nov. 7, 2025.
  
  [3] A. Habibović, V. M. Lundgren, J. Andersson, M. Klingegård, T. Lagström, A. Sirkka, J. Fagerlönn, C. Edgren, R. Fredriksson, S. Krupenia *et al.*, “Communicating intent of automated vehicles to pedestrians,” *Frontiers in Psychology*, vol. 9, p. 1336, 2018, doi: 10.3389/fpsyg.2018.01336.
  
  [4] D. Dey, A. Habibović, A. Löcken, P. Wintersberger, B. Pfleging, A. Riener *et al.*, “Taming the eHMI jungle: A classification taxonomy to guide, compare, and assess the design principles of automated vehicles’ external human–machine interfaces,” *Transportation Research Interdisciplinary Perspectives*, vol. 7, p. 100174, 2020, doi: 10.1016/j.trip.2020.100174.
  
  [5] J. Carmona, C. Guindel, F. Garcia, and A. de la Escalera, “eHMI: Review and guidelines for deployment on autonomous vehicles,” *Sensors*, vol. 21, no. 9, p. 2912, 2021, doi: 10.3390/s21092912.
  
  [6] M. Colley, M. Walch, and E. Rukzio, “Unveiling the lack of scalability in research on external communication of autonomous vehicles,” in *Proc. Extended Abstracts of the 2020 CHI Conf. on Human Factors in Computing Systems (CHI EA ’20)*, Honolulu, HI, USA, Apr. 2020, pp. 1–9, doi: 10.1145/3334480.3383010.

---

### <a id="hrc"></a>· Augmented Mobile Robots with Shared Perception in Uncertain Environments
[Mobile Automation and Sensing Systems (MASS) Lab](https://www.mass-lab-ut.com/) | The University of Texas at Austin  
📆 Sept. 2025 - Present  

<hr style="border: none; border-top: 1px dashed #aaa; margin: 1.2em 0;">

<div style="display: flex; justify-content: center; gap: 12px; flex-wrap: wrap;">
  <figure style="text-align:center; width:60%;">
    <img src="/assets/images/research_robot_system.png" alt="A=robot system" style="width:100%; border-radius:8px;">
    <figcaption>System Overview of the AR-Robot Platform</figcaption>
  </figure>
</div>

**Summary:** A human–robot collaboration framework that combines augmented reality (AR) and multi-modal sensing to achieve shared perception and intent understanding in uncertain, dynamic environments. The system enables mobile robots to visualize their surroundings—including obstacles, trajectories, and changes—through real-time AR interfaces, while interpreting human intent from gaze, gestures, and motion cues. By synchronizing AR headsets with robot perception data and creating an adaptive digital twin of the environment, the framework enhances transparency, situational awareness, and trust between humans and autonomous systems.  

**Keywords:** Human–Robot Collaboration (HRC), Shared Perception, Augmented Reality, Explainable AI, Digital Twin  

**Tools:**  
&nbsp;&nbsp;• **Hardware:** Clearpath Husky A200, Velodyne VLP-16 3D LiDAR, Azure Kinect Depth Cameras, Meta Quest Pro (IMU/face/hand tracking), Server Laptop   
&nbsp;&nbsp;• **Software:** Unity (C#), Python, ROS

<hr style="border: none; border-top: 1px dashed #aaa; margin: 1.2em 0;">

**Background:**  
Autonomous mobile robots now operate in campuses, hospitals, and public spaces. Despite strong perception and navigation, they often fail to communicate internal states, predictions, and intents to nearby humans in a transparent, cognitively meaningful way—leading to misjudged intent, over-reliance, and reduced trust. AR can visualize what robots “see/plan,” but most prior systems are one-way and overlook two-way communication and cognitive factors (trust, interpretability, situational awareness).  

**Problem:**  
We need a bi-directional channel where robots understand human intent (gaze, gestures, motion patterns) and humans intuitively grasp robot reasoning and environmental understanding. Bridging this gap demands an interdisciplinary, shared-perception architecture that fuses robotics/AI, AR visualization, and cognitive psychology.  

<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius:10px;">
  <iframe src="https://www.youtube.com/embed/pUWPkGKrnt0"
  title="AR–Robot Shared Perception Demo"
  style="position:absolute; top:0; left:0; width:100%; height:100%; border:0;"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
  allowfullscreen></iframe>
</div>
<p style="text-align:center;"><em>Demonstration video</em></p>

**Methodology: Overview**  
The system enables humans and robots to co-perceive and co-interpret complex scenes through AR devices synchronized with robot sensors, organized into three layers:

1. **Perceptual Layer** — Multi-modal sensing (LiDAR, cameras, IMU) for environment mapping, change detection, and trajectory prediction with AI-based reasoning.  
2. **Visualization Layer** — Real-time Digital Twin in AR renders robot-sensed semantics (obstacles, trajectories, salient changes) and uses LLM-assisted language cues to make insights human-understandable.  
3. **Cognitive Layer** — Measures human trust, interpretability, and response to adapt robot reasoning and human–robot communication (HRC) strategies.

**Methodology: Detail**

<div style="border:1px solid #ddd; background:#fafafa; padding:14px 16px; border-radius:10px; margin:12px 0;">
  <strong>System Development Phases</strong><br>
  (1) <b>System Integration & Setup</b><br>
  Mount 360° LiDAR and depth cameras on Husky; align AR Digital Twin; enable headset-to-robot intent cues (IMU/face/hand tracking).<br>
  📆 Sept. 2025 – Present<br>
  (2) <b>Field Data Collection & Benchmarking</b><br>
  Collect synchronized AR↔robot multi-modal data in pedestrian-dense areas; build an open benchmark for HRI and prediction.<br>
  📆 TBD <br>
  (3) <b>AR-Assisted Perception & Cognitive Evaluation</b><br>
  Run HRC tasks with LLM-integrated AR; evaluate trust calibration, latency, cognitive load, interpretability (e.g., HEXACO-based analysis).<br>
  📆 TBD <br>
  (4) <b>System Refinement & Dissemination</b><br>
  Fold cognitive results back into real-time HRC; prepare conference/journal submissions.<br>
  📆 TBD
</div>

**Results (Expected):**
- **Bi-directional HRC** where robots and humans exchange perceptual and intentional signals in real time.  
- **Open-source dataset** that couples AR-headset and robot sensors in crowded pedestrian environments.  
- **Measured gains** in trust calibration, situational awareness, and interpretability across controlled studies.


