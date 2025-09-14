# Marketing Mix Modeling with Google Mediation

## Overview

This repository presents a robust Marketing Mix Modeling (MMM) workflow, built to analyze the causal relationship between multiple marketing channels (social, search, direct response levers) and revenue, with a deep focus on **Google as a mediator**. Harnessing advanced statistical and machine learning strategies, this project provides actionable insights for optimal resource allocation across marketing channels.

---

## Problem Statement

Modern businesses deploy budgets across various digital and direct channels (Facebook, Instagram, Google, TikTok, Snapchat, Email/SMS, etc.), but quantifying each channel's impact on revenue and understanding mediated effects (such as how social influences search) is complex. 

**Objective:**  
- **Stage 1:** Explain and predict revenue using time-series marketing data, while respecting the causal mediation path where Google Search Ads act as a mediator of social and display channel influence.
- **Stage 2:** Quantify and model the incremental effect of Google as a mediator, accounting for Google-specific costs, and deliver causal business recommendations through a two-stage MMM framework.

---

## Data & Inputs

- **Input dataset:**  
  - 2 years of weekly data on spend across paid and organic channels, campaign costs, direct response marketing, average product price, platform follower growth, and total weekly revenue.
- **Key features:**  
  - Channel spend (Facebook, Google, TikTok, Instagram, Snapchat)
  - Email/SMS campaigns
  - Price & promotions
  - Social followers, weekly seasonality, trends

---

## Output

- **Stage 1:**  
  - Accurate baseline revenue predictions and direct attribution of marketing channels (excluding Google mediation for unbiased causal estimation).
  - Channel-wise ROI, feature importance, out-of-sample metrics (R², RMSE, MAPE).
  - Clean residuals (unexplained variance) ready for Stage 2 mediation analysis.

- **Stage 2:**  
  - Google mediation modeling: decomposition into direct, indirect (mediated), and total effects.
  - Explicit modeling of Google Ads platform fees, campaign management costs, and incremental revenues.
  - Final channel attribution, Google ROI, and strategic budget recommendations.

---

## Technologies Used

- **Python** (core analysis, feature engineering, modeling)
- **Google Colab** (cloud-based execution and reproducibility)
- **pandas, numpy** (data wrangling, engineering)
- **scikit-learn** (model selection, regression, evaluation)
- **scipy** (statistical testing)
- **matplotlib, seaborn** (EDA and model diagnostics)

---

## Market Analysis & Strategy

- **Causal MMM Approach:**
  - Avoids classical over-attribution by treating Google as an endogenous variable (mediator).
  - Applies adstock and saturation transforms to model real digital marketing dynamics.
  - Implements two-stage modeling (2SLS/mediation) to quantify both direct social/digital effects and indirect, Google-mediated effects.

- **Cost & ROI Modeling:**
  - Integrates real-world Google platform/management costs into ROI analysis.
  - Offers actionable, profit-maximizing channel allocation based on comprehensive attribution.
  - Enables precise planning for both direct conversions and "search uplift" from awareness campaigns.
  
- **Business Impact:**
  - Drives up to 15–40% performance uplift via optimal channel synergy (social+search).
  - Delivers clarity on when to scale Google investment (high mediation, strong ROI) vs. when to optimize social/direct levers.
  - Reduces ineffective spend by revealing diminishing returns and channel saturation points.

---

## Implementation Steps

**1. Data Preparation & Cleaning**
   - Handle missing data, zero-spend periods, outliers, and seasonal/cyclical trends.

**2. Feature Engineering**
   - Adstock (carryover) and saturation (diminishing returns) curves
   - Temporal lags, interaction terms, price-promotion effects

**3. Stage 1 Modeling**
   - Train/test split with time-series CV
   - Multi-model selection (Ridge, ElasticNet, Gradient Boosting)
   - Model diagnostics: cross-validated R², RMSE, MAPE, residual analysis

**4. Residual Extraction**
   - Isolate remaining (unexplained) variance for mediation analysis

**5. Stage 2 Mediation Modeling**
   - Predict Google spend using instrumental and causally relevant variables
   - Model Google-mediated revenue with explicit cost structure and synergy effects
   - Cross-validated model selection (choose best between Ridge, ElasticNet, GBM)
   - Attribution and mediation strength assessment, ROI calculation

**6. Insights & Recommendations**
   - Comparative charts/tables for direct vs. mediated impact
   - Strategic recommendations for budget allocation and channel coordination

---

## Results & Impact

- **Technical rigor:**  
  - Model delivers MAPE 20-35% on out-of-sample revenue, R² improvement with mediation accounted for.
  - Business-grade cost/ROI estimates on Google channel, with full attribution accountability.
- **Strategic clarity:**  
  - Quantifies marketing synergy and optimal spend mix.
  - Provides leadership with defensible recommendations, not just predictive vanity metrics.

---

## How to Reproduce

1. Clone this repository and open the included `.ipynb` notebook in Google Colab.
2. Upload your weekly structured marketing data CSV.
3. Run through the provided ordered cells for data cleaning, Stage 1, and Stage 2 modeling.

---

## License

Distributed under the MIT License. See `LICENSE` for more details.

---

## Contact

For questions, consult the [README instructions] or contact the original author.
