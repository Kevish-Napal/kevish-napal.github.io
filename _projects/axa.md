---
layout: page
title: Health inflation forecasting at AXA
description: Built a predictive analytics prototype to forecast short-term medical inflation using structured insurance and healthcare data. #The project focused on transforming complex business data into actionable forecasts to support decision-making.
img: assets/img/reconvertai/axa.png
importance: 2
category: Machine Learning
giscus_comments: false
---

**NOTE:** Project delivered under NDA; only non-confidential details are shared here.

As part of the Paris Digital Lab programme, I worked with AXA on a project focused on monitoring and forecasting health inflation in the UK. The project addressed a critical business challenge: an unexpected increase in healthcare costs had generated significant financial losses, creating a need for better analytical tools to anticipate future trends and support proactive decision-making.

The objective was to develop a data-driven monitoring solution capable of tracking health inflation over time, identifying changes in cost dynamics, and providing short-term forecasts. I contributed to the design and implementation of a predictive analytics workflow combining time series modelling and feature selection methods.

I used ARIMA models to forecast future health inflation trends from historical data, providing a statistical baseline for short-term prediction. In parallel, I applied machine learning methods, including Random Forest and Orthogonal Matching Pursuit, to identify the main factors associated with inflationary pressure. This helped move the analysis beyond simple forecasting by highlighting potential drivers of cost increases.

The resulting prototype provided AXA with a structured framework to monitor medical inflation, anticipate future cost trends, and better understand the variables contributing to healthcare cost escalation.

Keywords: time series analysis, forecasting, ARIMA, Random Forest, Orthogonal Matching Pursuit, feature selection, healthcare analytics, insurance analytics.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/reconvertai/axa-validation.png" title="Validation" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1: Model validation showing the agreement between predicted and observed health inflation trends.
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/reconvertai/axa-prediction.png" title="Prediction" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 2: Health inflation forecast for the year 2022, produced using data available in January 2022.
</div>



