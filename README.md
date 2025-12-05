# Multivariate Time Series Analysis for Predictive Analytics & Anomaly Detection Framework

This repository presents a comprehensive analysis and forecasting framework, utilizing multivariate time series techniques. The primary goal was to model and predict energy system consumption by rigorously accounting for external drivers (like temperature and price).

The methodology demonstrated here is **directly transferable to building robust anomaly detection systems** for financial data, such as payroll or accounting systems (Visma's domain).

## Core Project Relevance

The key to anomaly detection is defining "normal." This project achieves that through statistical modeling:

1.  **Modeling the Baseline ("Normal"):** The VAR/SARIMA models learn the normal patterns and dependencies within the data.
2.  **Identifying Deviations (Anomalies):** The difference between the model's prediction and the actual data is the **Residual**. In the context of payroll, a significant spike in the residual represents a potential *unexplained error* or anomaly that requires flagging and investigation.

##  Key Techniques Demonstrated

### 1. Root Cause & Causality Analysis
* **Granger Causality Testing:** Used to verify and quantify the directional influence between variables (e.g., "Does temperature statistically *cause* changes in load?").
    * *Relevance:* This skill is crucial for Visma's request to **"forklare hvorfor det skjedde"** (explain why it happened). It moves beyond simple correlation to determine leading factors behind an observed deviation.

### 2. Robust Modeling & Validation
* **Stationarity Testing (ADF, KPSS):** Ensuring the data meets the rigorous statistical requirements for VAR/SARIMA models, demonstrating a foundational understanding of time series statistics.
* **Multivariate Modeling (VAR):** Handling complex systems where multiple external variables affect the target, which is essential for accurate payroll forecasting (where salary is affected by hours, taxes, bonuses, etc.).
* **Seasonal Analysis (SARIMA):** Effectively capturing complex seasonal and yearly patterns inherent in the data.

### 3. Focus on Residual Analysis
The project concludes with a detailed analysis of the model's residuals.
* A key feature of the model is that major spikes in the residual plot are where the model fails to predict the actual value accurately—these are the **anomaly signals**.

## Repository Contents
| File Name | Description |
| :--- | :--- |
| `Analysis.ipynb` | The Jupyter Notebook containing the full end-to-end analysis, including data cleaning, testing, modeling, and results. |
| `Exam.csv` | The raw dataset used for the analysis. |
| `PowerSystem_Analysis.pdf` | The accompanying report providing theoretical context and conclusions. |

## 🚀 Getting Started
To run the analysis:

1.  Clone this repository.
2.  Install the required dependencies (e.g., `pandas`, `statsmodels`, `scikit-learn`).
3.  Open and run the `Analysis.ipynb` notebook.
