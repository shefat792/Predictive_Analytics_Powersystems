# Predictive Analytics and System Diagnostics: Time Series Analysis for Power Systems

This repository contains my Predictive Analytics exam project (PGR304), focusing on time-series analysis and forecasting for power-system data.

The project demonstrates a complete, end-to-end workflow: from statistical diagnosis and understanding of the dataset, to advanced model selection and evaluation. The core aim is to build a robust predictive model that serves as a **baseline for identifying deviations** and supporting **root cause analysis** in complex systems.

##  Repository Contents

* `Analysis.ipynb`: Jupyter notebook with the full analysis and modeling workflow.
* `Exam.csv`: The dataset used in the analysis.
* `PowerSystem_Analysis.pdf`: Written report summarizing methodology, results, and discussion.

##  Dataset (High Level)

Hourly observations with the following variables:

| Variable | Description |
| :--- | :--- |
| **Load_MW** (Target) | Total electricity consumption |
| **Temp_C** | Ambient temperature |
| **Price_DA_EUR_MWh** | Day-ahead electricity price |
| **Solar_MW** | Solar production |
| **Clouds_pct** | Cloud coverage percentage |

---

##  Methodological Overview

### Exploratory Data Analysis (EDA)
Summary statistics, outlier/scale checks, and visualizations (hourly + aggregated views).

### Time-series Diagnostics and Robustness
* **Stationarity Testing (ADF / KPSS):** Formal testing to ensure the statistical validity and **robustness** of the forecasting models.
* Handling strong 24-hour seasonality with seasonal differencing where relevant.
* Included preliminary work for **causal inference** to understand directional relationships between variables.

### Modeling & Selection
* **VAR (Vector Autoregression):** Utilized for multivariate forecasting, as it is effective at modeling the dynamic **interplay between multiple system components** (e.g., Load, Price, and Temp).
* **SARIMA/SARIMAX:** Used as a strong univariate baseline/benchmark.
* Model order/lag selection guided by **AIC/BIC** to optimize the balance between model fit and complexity.

### Evaluation and Deviation Analysis
* Forecast accuracy evaluated on a hold-out test window using MAE (Mean Absolute Error) and MAPE (Mean Absolute Percentage Error).
* The model's **Residuals** (errors) are analyzed, laying the groundwork for identifying **unexpected events** or outliers in the system that the model could not explain.

---

##  Key Results (From the report)

* VAR achieved the strongest performance on the test window (approx. MAE $\sim 725 \text{ MW}$, MAPE $\sim 2.85\%$).
* SARIMA performed weaker on the same horizon (approx. MAE $\sim 2500 \text{ MW}$, MAPE $\sim 10\%$).

##  How to Run

```bash
# Recommended: Create a virtual environment
python -m venv .venv

# Activate environment (Windows):
.venv\Scripts\activate

# Activate environment (macOS/Linux):
source .venv/bin/activate

# Install dependencies
pip install numpy pandas matplotlib seaborn scikit-learn statsmodels jupyter

# Start Jupyter Lab
jupyter lab

# Then open Analysis.ipynb and run all cells.
