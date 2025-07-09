# Regional Precipitation Forecasting in Israel Using Machine Learning

This project focuses on analyzing and forecasting precipitation across various regions in Israel by dividing the country into climatic zones and applying machine learning models to historical weather data.

##  Full Report (PDF)

[Precipitation_Analysis_Report.pdf](./Precipitation_Analysis_Report.pdf)
##  Overview

We analyzed rainfall data from weather stations across Israel, clustered them into meaningful climatic zones, and built Random Forest models to forecast regional precipitation. The goal was to understand rainfall variability across seasons and improve regional predictions using machine learning tools.

## 🔍 Methodology

### 1. Climatic Zoning
- Divided Israel into 4 climatic zones based on long-term precipitation and temperature data.
- Used clustering techniques to assign weather stations to the most appropriate zone, both annually and seasonally.
- Identified anomalies and stations that didn’t fit well — often due to microclimate influences.

### 2. Exploratory Data Analysis
- Analyzed seasonal and yearly averages.
- Generated anomaly maps to detect inconsistencies in the clustering.
- Evaluated the accuracy and limitations of the climatic division.

### 3. Forecasting with Random Forest
- Trained Random Forest Regressor models for each climatic zone.
- Used an 80/20 train/test split.
- Verified assumptions using:
  - Durbin-Watson for independence of errors
  - Q-Q plots for normality of residuals
  - ADF test for stationarity
  - Residual plots for homoscedasticity and nonlinearity

### 4. Evaluation
- Metrics: R², MAE, RMSE
- Found good training performance (R²: 0.68–0.82), but lower generalization on test data (R²: 0.22–0.52), indicating overfitting.
- The model struggled most with extreme precipitation values and regions with volatile climate.

## ⚒ Tools & Libraries

- Python
- pandas, matplotlib, scikit-learn, statsmodels
- Clustering: KMeans/Hierarchical (based on report context)
- Modeling: Random Forest Regressor
- Time Series Tests: Augmented Dickey-Fuller, Durbin-Watson

## Key Insights

- Annual clustering was more accurate than seasonal due to smoothing out extreme seasonal variability.
- A few stations consistently behaved as outliers due to geographical uniqueness (e.g., desert stations, coastal effects).
- Random Forest worked well for general trends, but future models need improvement to better handle extreme events and reduce overfitting.

