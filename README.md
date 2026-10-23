# 🚕 Taxi Demand Forecasting

Time series forecasting project to predict hourly airport taxi demand using **Linear Regression, Random Forest and LightGBM**, with a focus on seasonality, feature engineering and model performance.

## 📌 Context

Sweet Lift Taxi needs to anticipate taxi demand at airports to attract more drivers during peak hours.

By forecasting the number of orders for the next hour, the company can improve driver allocation and respond more efficiently to demand fluctuations.

## 🎯 Business Problem

The objective is to predict the number of taxi orders for the next hour using historical demand data.

The main evaluation requirement is:

**Test RMSE ≤ 48**

The project compares multiple machine learning models to identify the most accurate forecasting approach.

## 📊 Dataset

The project uses `taxi.csv`, containing historical taxi orders with timestamps.

- **Target:** `num_orders` — number of taxi orders
- **Time index:** Date and time of observation
- **Resampling:** Hourly aggregation using the sum of orders

The dataset is sorted chronologically and resampled into one-hour intervals before analysis.

## 🔎 Methodology

1. Data loading and quality checks
2. Hourly resampling
3. Exploratory time series analysis
4. Trend and seasonality decomposition
5. Rolling average analysis
6. Feature engineering using calendar variables and lag features
7. Chronological training, validation and test splits
8. Linear Regression baseline
9. Random Forest hyperparameter tuning
10. LightGBM hyperparameter tuning
11. Model comparison using RMSE
12. Final evaluation on unseen test data

## 📈 Exploratory Analysis

The analysis identified important temporal patterns:

- Taxi demand increased over the observed months.
- Demand exhibited daily seasonality.
- Higher order volumes occurred around midnight.
- Lower demand was observed during early morning hours.

These patterns support the use of time-based features for demand forecasting.

## 🛠️ Feature Engineering

The forecasting dataset includes:

- Calendar-based features
- Hour of day
- Day of week
- Lagged demand values
- Rolling average of previous observations

The model uses historical information to predict future demand without randomly shuffling the time series.

## 🤖 Machine Learning Models

Three regression approaches were evaluated.

### Linear Regression

Used as a baseline for comparison.

**Validation RMSE: 33.15**

### Random Forest

A nonlinear ensemble model evaluated using different hyperparameter configurations.

### LightGBM

A gradient boosting model optimized using different numbers of estimators and learning rates.

**Best validation RMSE: 31.96**

LightGBM was selected for the final evaluation.

## 🏆 Final Results

The selected LightGBM model achieved:

**Test RMSE: 41.72**

This result satisfies the project's requirement of an RMSE no greater than 48.

The model captures important variations in hourly demand, although prediction errors remain during some demand peaks.

## 💡 Key Findings

- Hourly aggregation provides a consistent forecasting frequency.
- Taxi demand exhibits trend and daily seasonality.
- Lag features help models capture recent demand behavior.
- Chronological data splitting is essential for time series forecasting.
- LightGBM achieved the strongest validation performance among the evaluated models.

## 🚀 Business Applications

The forecasting model could support:

- Driver allocation during peak demand
- Anticipation of busy airport periods
- Operational workforce planning
- Reduction of driver shortages
- More efficient demand management

## ⚠️ Limitations

The model uses historical order volumes and calendar information.

It does not explicitly account for external factors such as weather, flight schedules, airport disruptions or special events.

Performance should be monitored over time, especially if demand patterns change.

## 💻 Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Statsmodels
- LightGBM
- Jupyter Notebook

## 📁 Repository Structure

```text
taxi-demand-forecasting/
├── README.md
├── data/
│   └── taxi.csv
└── notebook/
    └── taxi_demand_forecasting.ipynb
```

## ▶️ Running the Project

Clone the repository and open the Jupyter Notebook located in the `notebook` directory.

The dataset is stored in the `data` directory.

Install the required Python libraries, including Pandas, NumPy, Matplotlib, Scikit-learn, Statsmodels and LightGBM.

---

### Author

**Brunno Almeida**

Data Science | Data Analytics | Python | SQL | Machine Learning
