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

## Tech Stack
- Python (Pandas, NumPy)
- Statsmodels (regression modeling)
- Matplotlib, Seaborn (visualization)

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