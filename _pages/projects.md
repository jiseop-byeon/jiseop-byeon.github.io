---
layout: single
title: "Projects"
author_profile: true
toc: true
toc_sticky: true
permalink: /projects/
---

<style>
.slider-container {
  width: 90%;
  margin: 25px auto;
  position: relative;
  overflow: visible;
}

.slider {
  display: flex;
  gap: 20px;
  overflow-x: scroll;
  scroll-snap-type: x mandatory;
  padding: 20px 0;
}

.slide {
  min-width: 60%;
  scroll-snap-align: center;
  position: relative;
}

.slide img {
  width: 100%;
  border-radius: 12px;
  box-shadow: 0 8px 20px rgba(0,0,0,0.2);
}

.view-btn {
  position: absolute;
  bottom: 15px;
  right: 15px;
  padding: 7px 12px;
  background: white;
  border-radius: 8px;
  border: 1px solid #ccc;
  cursor: pointer;
  font-size: 13px;
}

/* 🔥 캡션 추가 */
.caption {
  text-align: center;
  margin-top: 10px;
  font-size: 14px;
  color: #555;
  line-height: 1.4;
}
</style>

## 📂 Recent Projects

### <a id="bayesian"></a>· Bayesian Spatial Analysis of Bike-share Data for Cyclist Speed Zone Prediction in Austin, Texas  
📆 Jan. 2025 – Apr. 2025  

<div style="display: flex; flex-direction: column; align-items: center; gap: 20px;">
  <figure style="text-align:center; width:80%; margin:0;">
    <img src="/assets/images/project_bayesian_gam.png" 
         alt="Predicted speed map"
         style="width:100%; height:auto; border-radius:8px;">
    <figcaption>Our GAM’s predicted speed map by checkout location (given a fixed return kiosk).</figcaption>
  </figure>

  <figure style="text-align:center; width:80%; margin:0;">
    <img src="/assets/images/project_bayesian_jags.png" 
         alt="Trace and density plots"
         style="width:100%; height:auto; border-radius:8px;">
    <figcaption>Trace plots and density plots for one of our covariate coefficients and our tau variable.</figcaption>
  </figure>
</div>

**Summary:**  
This project applies Bayesian hierarchical modeling to predict average cyclist speeds in Austin’s MetroBike network. Using two City of Austin datasets — MetroBike Trips and MetroBike Kiosk Locations — the study integrates spatial coordinates of checkout and return kiosks to generate a continuous “speed map” across the city. By identifying high and low average speed zones, the model highlights potentially hazardous or congested routes for cyclists and provides actionable insights for urban mobility planning.  

**Keywords:**  
Bayesian Statistics, Spatial Modeling, Shared Mobility, Urban Safety  

**Tools:**  
&nbsp;&nbsp;• **Dataset:** [Austin MetroBike Trips](https://data.austintexas.gov/Transportation-and-Mobility/Austin-MetroBike-Trips/tyfh-5r8s/about_data), [Austin MetroBike Kiosk Locations](https://data.austintexas.gov/Transportation-and-Mobility/Austin-MetroBike-Kiosk-Locations/qd73-bsdg/about_data)  
&nbsp;&nbsp;&nbsp;&nbsp;– 100,000 sampled trips (2019 subset)  
&nbsp;&nbsp;&nbsp;&nbsp;– Excluded staff rebalancing trips and durations > 250 minutes  
&nbsp;&nbsp;• **Software:** R (+ JAGS), Python  

**Methodology:**  
- **Data Collection & Wrangling:** Combined the MetroBike trip data with kiosk locations to geocode checkout and return coordinates. Filtered unrealistic trip durations and missing records, and standardized the dataset for Bayesian modeling.  
- **Modeling:** Implemented a Bayesian Generalized Additive Model (GAM) and a Hierarchical Poisson Regression model using JAGS. Each kiosk’s longitude and latitude were encoded with Gaussian basis functions to capture spatial variability across Austin.  
- **Prior Settings:** Used weakly informative priors — β ∼ N(0, 100²I), τ ∼ Gamma(0.1, 0.1) — to allow data-driven posterior inference.  
- **Computation:** Conducted 50,000 MCMC iterations with 10,000 burn-in samples; convergence verified via Gelman-Rubin diagnostics.  

**Results:**  
The Bayesian GAM produced realistic spatial predictions of cyclist speed patterns, showing slower travel in downtown and denser urban areas. While the Poisson regression achieved better predictive accuracy for trip durations, the GAM effectively visualized spatial dependencies, forming the basis for city-scale risk mapping.  

**Future Work:**  
Refine the model with multimodal likelihoods to capture heterogeneous riding behaviors and integrate environmental covariates (e.g., elevation, weather, or time-of-day effects). Future versions will explore Gaussian Process or deep Bayesian models for more flexible spatial inference.  

---

### <a id="sarima"></a>· Weekly Traffic Flow Prediction using SARIMA: A Case Study of the Lamar–Manchaca Intersection in Austin, Texas  
  📆 Aug. 2024 – Dec. 2024  

<div style="display: flex; flex-direction: column; align-items: center; gap: 20px;">
  <figure style="text-align:center; width:80%; margin:0;">
    <img src="/assets/images/project_sarima_SBout_prediction.png" 
         alt="Traffic trend visualization"
         style="width:100%; height:auto; border-radius:8px;">
    <figcaption>SARIMA Prediction for Southbound-Out Direction at the Menchaca Intersection (1st Week of October).</figcaption>
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
📆 Aug. 2022 – Dec. 2022

<hr style="border: none; border-top: 1px dashed #aaa; margin: 1.2em 0;">

**Summary:**  
This project proposes MES (Mobility–Energy–Shopping), a future-ready urban infrastructure that transforms underutilized gas station sites in Seoul into vertically integrated Micro Fulfillment Centers (MFCs) combined with EV charging stations. Using public datasets—including population density, parcel area, delivery volume, and the spatial distribution of gas stations—the study identifies optimal sites and determines the required MFC scale for each location. Through data-driven spatial analysis and algorithmic modeling, the project presents a new typology for urban logistics and electric-mobility infrastructure in high-density cities.  

**Keywords:**  
EV Charging Infrastructure, Micro Fulfillment Center, Urban Logistics, Gas Station Reuse, Data-Driven Spatial Design  

**Tools:**  
  • Software: QGIS, Rhino 3D & Grasshopper (C# Scripting)  
  • Data: Public datasets on population, delivery volume, parcel areas, and all 472 gas station locations in Seoul  

**Methodology:**  

Data Collection: Compiled public data from Seoul Open Data Portal, including population by district, parcel sizes, delivery volume distribution, and gas station coordinates.  

Spatial Analysis:  
– Mapped gas station distribution and removed 39 irregular outliers for stable analysis.  
– Performed district-level comparison of population, parcel density, and delivery demand.  

Parametric Modeling (Rhino 3D & Grasshopper):  
– Modeled each station’s parcel geometry, land coverage, and floor-area ratio constraints.  
– Computed buildable volume and feasible vertical MFC capacity.  

Algorithmic Modeling:  
– Applied Voronoi spatial division to compute each station’s service territory.  
– Used custom C# scripts in Grasshopper to allocate required MFC area as weighted by service area, delivery volume, and parcel size.  
– Ranked and selected optimal sites (e.g., Gangnam-gu, Songpa-gu) based on aggregated scores.  

---

### <a id="luxury"></a>· Luxury Residential House Design in Itaewon-dong 258-66, Seoul, Korea  
ARE3080. Architectural Integrated Design I | Hanyang University  
📆 Mar. 2022 - Jun.2022  

<hr style="border: none; border-top: 1px dashed #aaa; margin: 1.2em 0;">

Architectural design of a luxury family residence in Itaewon reflecting the lifestyle needs of a five-member household, using AutoCAD, Revit, and SketchUp for site analysis, legal review, and 3D visualization.


#### ① Site Analysis  
A comprehensive study of the project’s physical, environmental, and regulatory context, structured as follows:

<div style="border:1px solid #ddd; background:#fafafa; padding:16px 20px; border-radius:10px; margin:18px 0;">
  <ul style="margin:0; padding-left:18px;">

    <li><strong>History</strong></li>

    <li><strong>Information</strong>
      <ul style="margin-top:6px; padding-left:18px;">
        <li>Landmarks & Institutions</li>
        <li>Topography & Weather</li>
      </ul>
    </li>

    <li><strong>Regulation</strong>
      <ul style="margin-top:6px; padding-left:18px;">
        <li>Regulatory Review, Land Price, Existing Building</li>
      </ul>
    </li>

    <li><strong>Accessibility</strong>
      <ul style="margin-top:6px; padding-left:18px;">
        <li>Roads & Public Transportation</li>
      </ul>
    </li>

    <li><strong>SWOT Analysis</strong></li>

  </ul>
</div>


Full slide elaborating on the site analysis:

<div class="slider-container">
  <div class="slider">

    <!-- 1–10 -->
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0001.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0001.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0002.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0002.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0003.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0003.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0004.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0004.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0005.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0005.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0006.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0006.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0007.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0007.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0008.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0008.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0009.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0009.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0010.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0010.jpg"></a></div>

    <!-- 11–20 -->
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0011.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0011.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0012.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0012.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0013.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0013.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0014.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0014.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0015.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0015.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0016.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0016.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0017.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0017.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0018.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0018.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0019.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0019.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0020.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0020.jpg"></a></div>

    <!-- 21–30 -->
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0021.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0021.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0022.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0022.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0023.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0023.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0024.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0024.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0025.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0025.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0026.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0026.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0027.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0027.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0028.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0028.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0029.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0029.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/site_analysis/site_analysis_page-0030.jpg" target="_blank"><img src="/assets/images/luxury/site_analysis/site_analysis_page-0030.jpg"></a></div>

  </div>
</div>

---

#### ② Design Concept  
The design concept is grounded in the diverse lifestyles of the five residents and the way their daily routines inform spatial needs and shared interactions. It is organized into two key components:

<div style="border:1px solid #ddd; background:#fafafa; padding:16px 20px; border-radius:10px; margin:18px 0;">
  <ul style="margin:0; padding-left:18px;">
    <li><strong>Residence Information</strong></li>
    <li><strong>Room Arrangement Strategy</strong></li>
  </ul>
</div>

Full slide summarizing the design concept:

<div class="slider-container">
  <div class="slider">

    <div class="slide"><a href="/assets/images/luxury/design_concept/design_concept_page-0001.jpg" target="_blank"><img src="/assets/images/luxury/design_concept/design_concept_page-0001.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/design_concept/design_concept_page-0002.jpg" target="_blank"><img src="/assets/images/luxury/design_concept/design_concept_page-0002.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/design_concept/design_concept_page-0003.jpg" target="_blank"><img src="/assets/images/luxury/design_concept/design_concept_page-0003.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/design_concept/design_concept_page-0004.jpg" target="_blank"><img src="/assets/images/luxury/design_concept/design_concept_page-0004.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/design_concept/design_concept_page-0005.jpg" target="_blank"><img src="/assets/images/luxury/design_concept/design_concept_page-0005.jpg"></a></div>

    <div class="slide"><a href="/assets/images/luxury/design_concept/design_concept_page-0006.jpg" target="_blank"><img src="/assets/images/luxury/design_concept/design_concept_page-0006.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/design_concept/design_concept_page-0007.jpg" target="_blank"><img src="/assets/images/luxury/design_concept/design_concept_page-0007.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/design_concept/design_concept_page-0008.jpg" target="_blank"><img src="/assets/images/luxury/design_concept/design_concept_page-0008.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/design_concept/design_concept_page-0009.jpg" target="_blank"><img src="/assets/images/luxury/design_concept/design_concept_page-0009.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/design_concept/design_concept_page-0010.jpg" target="_blank"><img src="/assets/images/luxury/design_concept/design_concept_page-0010.jpg"></a></div>

  </div>
</div>

---

#### ③ Drawings (Written in Korean)
This section presents the complete architectural drawing set, including plans, elevations, and sections that illustrate the spatial configuration and formal resolution of the project.

<div style="border:1px solid #ddd; background:#fafafa; padding:16px 20px; border-radius:10px; margin:18px 0;">
  <ul style="margin:0; padding-left:18px;">
    <li><strong>Site Plan</strong></li>
    <li><strong>Floor Plans</strong></li>
    <li><strong>Front Elevation</strong></li>
    <li><strong>Right Elevation</strong></li>
    <li><strong>Rear Elevation</strong></li>
    <li><strong>Left Elevation</strong></li>
    <li><strong>Bird’s-eye & Perspective Views</strong></li>
  </ul>
</div>

<div class="slider-container">
  <div class="slider">

    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0001.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0001.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0002.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0002.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0003.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0003.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0004.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0004.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0005.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0005.jpg"></a></div>

    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0006.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0006.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0007.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0007.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0008.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0008.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0009.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0009.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0010.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0010.jpg"></a></div>

    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0011.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0011.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0012.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0012.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0013.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0013.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0014.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0014.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0015.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0015.jpg"></a></div>

    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0016.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0016.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0017.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0017.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0018.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0018.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0019.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0019.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0020.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0020.jpg"></a></div>

    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0021.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0021.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0022.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0022.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0023.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0023.jpg"></a></div>
    <div class="slide"><a href="/assets/images/luxury/drawings/drawings_page-0024.jpg" target="_blank"><img src="/assets/images/luxury/drawings/drawings_page-0024.jpg"></a></div>

  </div>
</div>



