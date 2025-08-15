# Time-Series-Forecasting-of-PJME-Energy-Demand-using-XGBoost

## 📌 Overview
This project forecasts **hourly PJME (PJM East) energy demand in megawatts (MW)** using machine learning.  
It uses **time series feature engineering** combined with **XGBoost regression** to predict future energy consumption based on historical demand patterns.  
The workflow covers **data preprocessing, visualization, model training, evaluation, and insights**.

---

## 📂 Dataset
- **Name:** PJME Hourly Energy Consumption  
- **Source:** PJM Interconnection (public dataset)  
- **Description:** Hourly energy demand in MW for the PJM East region over multiple years.  
- **File:** `PJME_hourly.csv`

---

## 🛠️ Workflow & Features
### 1. **Data Preprocessing**
- Convert `Datetime` column to pandas datetime format.
- Set `Datetime` as the index for time series operations.
- Chronologically split into **Training Set** (before 2015) and **Test Set** (2015 onward).
- Create time-based features:
  - `hour`, `dayofweek`, `quarter`, `month`, `year`, `dayofyear`, `dayofmonth`, `weekofyear`.

### 2. **Exploratory Data Analysis**
- Long-term trend plots to observe demand fluctuations over years.
- Weekly zoom-in views to analyze short-term variations.
- **Boxplot by Hour** to study intraday demand cycles.

### 3. **Modeling**
- **Algorithm:** XGBoost Regressor (`reg:squarederror` objective).
- **Key Parameters:**
  - `n_estimators=1000`
  - `learning_rate=0.01`
  - `max_depth=3`
  - `early_stopping_rounds=50`
- **Training:** Evaluated on both training and test sets for early stopping.

### 4. **Evaluation**
- **Metric:** Root Mean Squared Error (RMSE)
- Feature importance visualization to identify most predictive features.
- Daily average error ranking for worst-performing dates.

---

## 📊 Visualizations
1. **Energy Demand Over Time** — Full dataset plotted with historical trends.
2. **Train/Test Split** — Clear separation with vertical marker.
3. **Boxplot: MW by Hour** — Shows intraday demand patterns.
4. **Predicted vs. Actual Energy Demand** — Overlay of forecasts on real data.
5. **Weekly Forecast Example** — Zoomed-in comparison for one week.
6. **Feature Importance** — Bar chart showing top contributing features to the model.

---

## 💻 Installation
```bash
git clone https://github.com/your-username/pjme-energy-forecasting.git
cd pjme-energy-forecasting
pip install -r requirements.txt
