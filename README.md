#  Weighted Aging Curve Model: MLB Batting Analysis (2000-2024)

**Project Goal:** To accurately quantify the average rate of offensive performance change in MLB batters, providing a reliable aging factor for use in player valuation and projection systems.

## Key Statistical Findings

| Metric | Result | Interpretation |
| :--- | :--- | :--- |
| **Aging Coefficient** | **-0.00106** | The model predicts an average decline of 0.00106 wOBA points per year of age. |
| **Model Accuracy (RMSE)** | **0.04443** | The average prediction error for a player's year-over-year wOBA change. |
| **Statistical Significance** | **p < 0.001** | The effect of Age on performance change is highly significant. |
| **Estimated Peak Age** | **~24.5 Years** | The age at which the linear trend predicts $\text{wOBA\_delta} = 0$. |

## Methodology

1.  **Data Source:** Historical season-level data (2000-2024) was retrieved using the stable **`Lahman`** R package.
2.  **Core Metric:** We calculated **Weighted On-Base Average ($\text{wOBA}$)**, the industry standard for offensive value.
3.  **Modeling Technique:** We employed the **Delta Method** with **Weighted Linear Regression** ($\mathbf{wOBA\_delta \sim Age}$).
4.  **Bias Mitigation:** The model was heavily **weighted** by $\mathbf{\min(PA_{X},\, PA_{X-1})}$ to mitigate the influence of small sample sizes and control for **Survivorship Bias**.

5.  ## Project Deliverables and Tools

| Component | Status | Link / File |
| :--- | :--- | :--- |
| **Final Visualization** (Interactive Dashboard) | Published | [Weighted Delta Aging Curve: MLB Batting](https://public.tableau.com/app/profile/charlie.hildbold/viz/WeightedDeltaAgingCurveMLBBatting/Dashboard1) |
| **Full R Code** | Complete | `weighted_aging_curve.ipynb` |
| **Tools Used** | R (`tidyverse`, `Lahman`, `tidymodels`), Tableau Public | |
