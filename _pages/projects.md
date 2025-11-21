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
📆 Aug. 2022 - Dec.2022  

<hr style="border: none; border-top: 1px dashed #aaa; margin: 1.2em 0;">

Statistical modeling of shared mobility usage patterns.

---

### <a id="luxury"></a>· Luxury Residential House Design in Itaewon-dong 258-66, Seoul, Korea  
ARE3080. Architectural Integrated Design I | Hanyang University  
📆 Mar. 2022 - Jun.2022  

#### ① Site Analysis  

<div style="border:1px solid #ddd; background:#fafafa; padding:16px 20px; border-radius:10px; margin:18px 0;">
  <p>A comprehensive study of the project’s physical, environmental, and regulatory context, structured as follows:</p>

  <ul>
    <li><strong>History</strong><br>
      Historical evolution of Itaewon-dong and past development patterns.
    </li>

    <li><strong>Information</strong><br>
      Key contextual attributes shaping the site’s development potential, including:
      <ul style="margin-top:6px;">
        <li><strong>Landmarks & Educational Institutions</strong> — Cultural anchors and service facilities within the neighborhood.</li>
        <li><strong>Topography & Slope Characteristics</strong> — Terrain profile and elevation differences influencing circulation and massing.</li>
        <li><strong>Weather & Micro-Climate</strong> — Sunlight, prevailing winds, and seasonal comfort considerations.</li>
      </ul>
    </li>

    <li><strong>Regulation</strong><br>
      Permissible actions, construction laws, land price distribution, and existing building conditions.
    </li>

    <li><strong>Accessibility</strong><br>
      Road hierarchy, public transportation network, and population density.
    </li>

    <li><strong>SWOT Analysis</strong><br>
      Strengths, weaknesses, opportunities, and threats derived from the site’s physical and socioeconomic context.
    </li>
  </ul>

  <p style="margin-top:12px; margin-bottom:0;">Full slide elaborating on the site analysis:</p>
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

<div style="border:1px solid #ddd; background:#fafafa; padding:16px 20px; border-radius:10px; margin:18px 0;">
  <p>The design concept is grounded in the diverse lifestyles of the five residents and the way their daily routines inform spatial needs and shared interactions. It is organized into two key components:</p>

  <ul>
    <li><strong>Residence Information</strong><br>
      Outlines each family member’s background and required spaces — including a professional kitchen, a private home office, a sound-isolated music room, a creative workspace, and safe play areas — forming the foundation for programmatic zoning.
    </li>

    <li><strong>Room Arrangement Strategy</strong><br>
      Establishes a hierarchy of private, transitional, and social spaces inspired by a cabin-like spatial quality, where boundaries shift fluidly between indoors and outdoors. The arrangement balances privacy with communal life, organizing functions around a central family zone for natural circulation and connection.
    </li>
  </ul>

  <p style="margin-top:12px; margin-bottom:0;">Full slide summarizing the design concept:</p>
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

