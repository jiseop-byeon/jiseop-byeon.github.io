---
layout: single
title: "Projects"
author_profile: true
toc: true
toc_sticky: true
permalink: /projects/
---

## 📂 Recent Projects

### <a id="bayesian"></a>· Bayesian Spatial Analysis of Bike-share Data for Cyclist Speed Zone Prediction in Austin, Texas  
SDS384. Bayesian Statistical Methods | The University of Texas at Austin  
📆 Jan. 2025 - Apr.2025  

<hr style="border: none; border-top: 1px dashed #aaa; margin: 1.2em 0;">

Reinforcement Learning approach for urban mobility optimization.

---

### <a id="sarima"></a>· Weekly Traffic Flow Prediction using SARIMA: A Case Study of the Lamar–Manchaca Intersection in Austin, Texas  
  📆 Aug. 2024 – Dec. 2024  

<div style="display: flex; flex-direction: column; align-items: center; gap: 20px;">
  <figure style="text-align:center; width:80%; margin:0;">
    <img src="/assets/images/project_sarima_NBprediction.png" 
         alt="Traffic trend visualization"
         style="width:100%; height:auto; border-radius:8px;">
    <figcaption>SARIMA Prediction for Northbound-In Direction at the Menchaca Intersection (1st Week of October).</figcaption>
  </figure>
</div>
  
  **Summary:**  
  This project analyzes short-term traffic flow patterns at the Lamar–Manchaca intersection in Austin using a Seasonal Autoregressive Integrated Moving Average (SARIMA) model. By applying 15-minute interval radar data from the City of Austin Open Data Portal, the study successfully forecasts one week of traffic volume trends, identifying recurring daily and weekly traffic patterns and peak-hour behaviors.  

  **Keywords:**  
  Traffic Forecasting, Time-Series Analysis, SARIMA, Urban Mobility, Austin Transportation  

  **Tools:**  
  &nbsp;&nbsp;• **Dataset:** [Radar Traffic Counts](https://data.austintexas.gov/Transportation-and-Mobility/Wavetronix-Traffic-Sensors/xecs-rpy9/about_data)  
  &nbsp;&nbsp;&nbsp;&nbsp;– 15-minute interval traffic counts  
  &nbsp;&nbsp;&nbsp;&nbsp;– 4 directional flows: NB_in, NB_out, SB_in, SB_out  
  &nbsp;&nbsp;&nbsp;&nbsp;– Training: Sept 2020 (30 days)  
  &nbsp;&nbsp;&nbsp;&nbsp;– Testing: Oct 2020 (7 days)  
  &nbsp;&nbsp;• **Software:** Python, Excel  

  **Methodology:**  
  - **Data Cleaning:** Identified and corrected missing and duplicate records at non-15-minute intervals. Missing data were imputed using one-week-apart values to preserve weekly periodicity.  
  - **Exploratory Analysis:** Quantified variability and central tendencies for each traffic direction; identified SB_in as the most volatile direction.  
  - **Modeling:** Implemented SARIMA with parameters (p,d,q) = (1,1,1) and (P,D,Q,m) = (1,1,1,96) to capture both daily and weekly cycles.  
  - **Evaluation:** Forecasted Oct 1–7, 2020 traffic volumes and validated using Mean Squared Error (MSE ≤ variance criterion). All four traffic directions met this condition.  

  **Results:**  
  SARIMA effectively modeled diurnal and weekly patterns, achieving low prediction errors (e.g., SB_out MSE = 129.52 < variance = 1634.33). The model demonstrated strong generalization for consistent flow directions, highlighting SARIMA’s applicability for real-time congestion prediction.  

  **Future Work:**  
  Integrate external factors (weather, events, holidays) and explore hybrid or deep learning approaches (e.g., LSTM, Prophet) to capture non-linear and irregular patterns for more adaptive traffic forecasting.  

---

### <a id="mfc"></a>· Optimal Sites and Scale Selection for Micro Fulfillment Center (MFC) Construction in Seoul, Korea  
ARE5009. Adventure Design II | Hanyang University  
📆 Aug. 2022 - Dec.2022  

<hr style="border: none; border-top: 1px dashed #aaa; margin: 1.2em 0;">

Statistical modeling of shared mobility usage patterns.

---

### <a id="luxury"></a>· Luxury Residential House Design in Itaewon-dong 258-66, Seoul, Korea  
ARE3080. Architectural Integrated Design I | Hanyang University  
📆 Mar. 2022 - Jun.2022  

Efficient hybrid CNN–Transformer for mobile medical imaging.
