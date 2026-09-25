# cmapss-predictive-maintenance
End-to-end predictive maintenance pipeline on NASA C-MAPSS (FD001) using Random Forest to predict turbofan engine Remaining Useful Life (RUL). 

# ✈️ Turbofan Engine Remaining Useful Life (RUL) Prediction

## 📌 Overview
An end-to-end machine learning predictive maintenance pipeline built on NASA's C-MAPSS dataset (`FD001`). The model leverages feature engineering on multi-sensor degradation signals to predict the Remaining Useful Life (RUL) of aircraft engines before failure.

## 🛠️ Pipeline Architecture
1. **Preprocessing & Feature Selection:** Dropped flat/zero-variance sensor channels and normalized active features using `MinMaxScaler`.
2. **Feature Engineering:** Computed 20-cycle rolling means and standard deviations per `unit_id` to provide temporal context to time-series degradation.
3. **Target Transformation:** Applied piecewise upper-limit RUL clipping at 125 cycles.
4. **Model:** `RandomForestRegressor` evaluated on the last recorded cycle of 100 test engine units.

## 📊 Results
Evaluated against ground truth labels (`RUL_FD001.txt`):
* **RMSE:** 20.84 cycles
* **MAE:** 14.25 cycles

## 🚀 How to Run
1. Clone the repository:
   ```bash
   git clone [https://github.com/your-username/cmapss-predictive-maintenance.git](https://github.com/your-username/cmapss-predictive-maintenance.git)
