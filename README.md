# ✈️ Turbofan Engine Remaining Useful Life (RUL) Prediction

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Mez-MohamedRafik/cmapss-predictive-maintenance/blob/main/Engine_Failure_RFR_predict.ipynb)

## 📌 Overview
An end-to-end machine learning predictive maintenance pipeline built on NASA's C-MAPSS dataset (`FD001`). The model leverages feature engineering on multi-sensor degradation signals to predict the Remaining Useful Life (RUL) of aircraft engines before failure.

## 🛠️ Pipeline Architecture
1. **Preprocessing & Feature Selection:** Dropped flat/zero-variance sensor channels (e.g., `sensor_10`) and normalized active features using `MinMaxScaler`.
2. **Feature Engineering:** Computed 20-cycle rolling means and standard deviations per `unit_id` to capture temporal sensor degradation trends.
3. **Target Transformation:** Applied piecewise upper-limit RUL clipping at 125 cycles to reflect realistic early-lifecycle behavior.
4. **Model:** `RandomForestRegressor` evaluated on the final recorded cycle of 100 test engine units.

## 📊 Results
Evaluated against NASA ground truth labels (`RUL_FD001.txt`):
* **RMSE:** 20.84 cycles
* **MAE:** 14.25 cycles

## 🚀 How to Run

Click the **Open in Colab** badge above or click [here](https://colab.research.google.com/github/Mez-MohamedRafik/cmapss-predictive-maintenance/blob/main/Engine_Failure_RFR_predict.ipynb) to execute the interactive notebook in your browser.

### Option 2: Run Locally
1. Clone the repository:
   ```bash
   git clone [https://github.com/Mez-MohamedRafik/cmapss-predictive-maintenance.git](https://github.com/Mez-MohamedRafik/cmapss-predictive-maintenance.git)
