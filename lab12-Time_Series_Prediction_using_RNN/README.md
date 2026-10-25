# Lab12 – Time Series Prediction with RNNs

## Theoretical Background

**Time Series Preparation**

* Hourly data must form a regular grid: missing timestamps are added with `resample('h')`, then filled per column type – counts with `0`, sensor readings by interpolation, categorical values by forward fill.
* Targets are scaled (counts divided by 1000) to keep values in a range suitable for gradient-based training.
* `timeseries_dataset_from_array` turns a series into sliding windows (here 24 hours) paired with the next value as the target.
* Data are split chronologically (train: 2011-01 – 2012-06, validation: 2012-07 – 2012-12) – never shuffled across time.

**Naive Baselines**

* Predict the value from the same hour one day earlier (`shift(24)`) or one week earlier (`shift(168)`).
* Any learned model should beat these baselines to be worth using.

**Recurrent Neural Networks**

* **LSTM** cells keep an internal state across time steps, which lets them model dependencies inside the input window.
* A single-unit LSTM returns its state directly as the prediction; a wider LSTM (32 units) followed by a `Dense(1)` layer has much more capacity.
* **Deep RNN:** stacked LSTM layers with `return_sequences=True` on all but the last one.
* **Multivariate input:** extra features (`atemp`, `weathersit`, `workingday`) are fed alongside the target series in every time step.
* Models were trained with SGD (momentum 0.9) and the Huber loss, which is less sensitive to outliers than MSE.

---

## Conclusions

* **Dataset:** UCI Bike Sharing (hourly rentals, 2011–2012); 165 missing hours were filled to get 17 544 regular samples.
* **Validation MAE (rentals per hour):**

  | Model | MAE |
  |---|---|
  | Naive – same hour yesterday | 63.8 |
  | Naive – same hour last week | **52.4** |
  | Dense (linear, 24 h window) | 55.9 |
  | LSTM(1) | 104.5 |
  | LSTM(32) + Dense | 87.9 |
  | Deep RNN (3 × LSTM(32)) | 80.0 |
  | Multivariate LSTM(32) | 81.8 |

* **Linear model wins among trained models:** a single dense layer over the last 24 hours beat every RNN variant.
* **RNN capacity matters:** LSTM(1) was the weakest model; adding units and depth steadily reduced the error.
* **Extra features helped only a little:** the multivariate model did slightly better than the univariate LSTM(32) but not better than the deep RNN.
* **Weekly seasonality is key:** the weekly naive baseline was the best overall – a 24-hour window cannot see the weekly pattern, so longer input windows would be the next step.

---
