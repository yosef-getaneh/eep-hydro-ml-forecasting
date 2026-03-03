Machine Learning-Based Hydropower Forecasting Dashboard for Ethiopian Electric Power (EEP)

Overview

This project develops a Machine Learning-Based Hydropower Forecasting Dashboard to support operational and planning activities at Ethiopian Electric Power (EEP). Hydropower supplies approximately 90% of Ethiopia’s electricity through major plants like Gibe, GERD, Tekeze, and others. The dashboard integrates operational data from 14 hydropower plants (2013-2025) and meteorological data to forecast key variables such as reservoir water levels, actual energy production, discharge water, and min/max unit loads.
A comprehensive data preprocessing pipeline handles date standardization, missing values, outlier mitigation using IQR capping, feature scaling, and selection to reduce multicollinearity. Multiple regression models (e.g., Gradient Boosting, Random Forest, XGBoost) are trained for multi-output forecasting. Performance is evaluated using MAE, RMSE, and R² metrics.
The interactive Dash-based web application provides:

Dynamic plant selection and forecast horizons.
Visualizations: Actual vs. predicted time-series, boxplots for outliers, and 365-day ahead forecasts (2026-2030).
Anomaly detection flagging deviations >5%.
Tabular outputs for decision-making.

This system enhances grid stability, resource optimization, efficiency, and data-driven planning in Ethiopian hydropower operations.
Keywords: Hydropower Forecasting, Ethiopian Electric Power, Machine Learning, Gradient Boosting, Random Forest, XGBoost, Multi-Output Regression, Anomaly Detection, Interactive Dashboard, Time Series Prediction.
Authors

Table of Contents

Overview
Installation
Usage
Data
Methodology
Models
Dashboard Features
Results
Challenges and Limitations
Future Work
References
Appendices
License
Contributing
Contact

Installation
Prerequisites

Python 3.8+
Virtual environment (recommended: venv or conda)

Steps

Clone the repository:textgit clone https://github.com/yourusername/eep-hydropower-forecasting.git
cd eep-hydropower-forecasting
Create and activate a virtual environment:textpython -m venv env
source env/bin/activate  # On Windows: env\Scripts\activate
Install dependencies:textpip install -r requirements.txt(Assumed requirements.txt includes: pandas, numpy, scikit-learn, xgboost, plotly, dash, etc. Generate it with pip freeze > requirements.txt if needed.)
Download datasets (not included in repo due to size; contact authors for access):
Place CSV files for 14 hydropower plants in /data/ directory.


Usage

Run the dashboard:textpython app.py
Open http://127.0.0.1:8050/ in your browser.

Select a hydropower plant (e.g., Gibe I).
Choose forecast horizon (short/medium-term).
View predictions, visualizations, and anomalies.

For model training (optional):
textpython train_models.py

Outputs saved models in /models/.

See APPENDIX B: DASHBOARD USER GUIDE for detailed instructions.
Data

Power Plants Dataset: Operational data from 14 plants (e.g., Gibe I-III, GERD, Tekeze, etc.) spanning 2013-2025.
Meteorological Data: Integrated from sources like NASA for rainfall, temperature, etc.
Preprocessing: Duplicate handling, date-time conversion (GC/EC), non-numeric conversion, column cleaning, feature engineering (lags), missing value imputation, outlier capping (IQR), correlation analysis.
See APPENDIX C: DATA DICTIONARY and APPENDIX C: DESCRIPTIVE STATISTICS FOR GIBE I DATASET.

Methodology

Data Collection: Power plant and meteorological datasets.
Preprocessing: Overview, duplicates, date standardization, conversions, cleaning, engineering, missing values (imputation), outliers (IQR winsorization), correlation, lag features, target selection, train-test split.
Models: Multi-output regression with configurations for RF, GB, XGBoost, etc.
Evaluation: R², MSE, RMSE, MAE, performance comparison.

Models

Random Forest (RF)
Gradient Boosting (GB)
XGBoost (XGB)
Others explored: SVR, KNN, DT, LR.

Trained for targets: Reservoir water level, energy production, discharge, min/max load.
Feature importance implications discussed in report.
Dashboard Features

User Interface: Interactive web app with plant selection, forecast controls.
Visualizations: Time-series plots (actual vs. predicted), diagnostic boxplots, tabular forecasts (2026-2030).
Anomaly Detection: Flags deviations exceeding 5%.
Example: Ethiopian Electric Power Plant Forecast Dashboard - Gibe 1 Water Level Prediction (interface and table).

Results

Short- and medium-term forecasts for 2026-2030.
Improved operational decision-making, efficiency, and reliability.

Challenges and Limitations

Data quality issues (missing values, inconsistencies).
Nonlinear interactions and climate variability.
Scope limited to 14 plants; no real-time integration.

Future Work

Integrate real-time SCADA/API data.
Incorporate advanced ML (e.g., deep learning).
Expand to more variables and plants.
Deploy to cloud for broader access.

References
(Include key citations from literature review on hydropower forecasting, ensemble methods, etc. Full list in project report.)
Appendices

B: Dashboard User Guide - Step-by-step usage.
C: Data Dictionary - Variable descriptions.
C: Descriptive Statistics for Gibe I Dataset - Stats summary.

License
This project is licensed under the MIT License - see the LICENSE file for details.
Contributing
Contributions welcome! Fork the repo, create a branch, and submit a pull request. Follow code style guidelines.

Contact
For questions, contact:

Yosef Getaneh:getanehyosef78@gmail.com
