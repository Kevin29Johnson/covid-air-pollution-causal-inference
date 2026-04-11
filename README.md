# COVID Air Pollution Causal Inference

## Overview
This project analyzes the impact of COVID-19 lockdown policies on urban air pollution using a **causal inference framework**. Specifically, it estimates whether countries with stricter lockdowns experienced larger changes in air quality compared to those with weaker restrictions.

We implement a **Difference-in-Differences (DiD)** approach to isolate the effect of lockdowns by comparing:
- Pre vs post COVID periods  
- Treated (high stringency) vs control (low stringency) countries  

---

## Methodology
- Defined treatment groups using the **Oxford COVID-19 Stringency Index**
- Constructed a panel dataset with city-level AQI observations (2019–2021)
- Created key variables:
  - `treated`: high vs low lockdown intensity  
  - `post`: before vs after March 2020  
  - `did`: interaction term (treated × post)  
- Estimated causal effect using **OLS regression (DiD model)**  
- Validated assumptions through **trend visualization**

---

## Key Result
Countries with stricter lockdowns experienced an additional **~12 AQI unit reduction** compared to control countries (statistically significant).

---

## Visualizations
The `notebooks/visualizations.ipynb` notebook produces a rich set of figures:

1. **Animated World Heatmap** — interactive Plotly scatter-geo showing weekly relative AQI change per city with a play/pause slider  
2. **World Heatmap GIF** — static bi-weekly frames compiled into a looping GIF via matplotlib  
3. **AQI Time-Series** — monthly average AQI by country and 7-day rolling AQI for key cities (Delhi, New York, London, Paris, Berlin)  
4. **Causal Inference Plots** — parallel trends, DiD group means, country-level pre/post slopes, and monthly DiD gap over time  

All figures are saved to `outputs/figures/`.

---

## Tech Stack
- Python (Pandas, NumPy)
- Statsmodels (regression modeling)
- Matplotlib, Seaborn, Plotly (visualization)
- Pillow & Kaleido (GIF / static image export)

---

## Structure
- `data/raw` — original datasets  
- `data/clean` — processed and merged dataset  
- `notebooks` — analysis and modeling notebooks  
- `outputs` — plots and results  

---

## Notes
- AQI used as primary outcome due to missingness in PM2.5  
- Treatment assignment based on external policy data (not outcome-based)  
- Results should be interpreted with consideration of baseline differences and seasonal effects  