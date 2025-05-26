# Lab10 – Hyperparameter Tuning for Neural Networks

## Theoretical Background

**Hyperparameters** are settings of a model that are not learned during training but significantly impact its performance and convergence, such as the number of hidden layers, number of neurons per layer, optimizer type, and learning rate.

**Randomized Search with scikeras:**  
- Uses scikit-learn’s `RandomizedSearchCV` wrapper around a Keras model (`KerasRegressor`) to randomly sample hyperparameter combinations from defined distributions.  
- Employs cross-validation (e.g., 3-fold) to robustly estimate model performance.  
- EarlyStopping callback is used to prevent overfitting and reduce unnecessary epochs.

**Keras Tuner:**  
- Provides a dedicated interface to search hyperparameter space using strategies like random search or Bayesian optimization.  
- Hyperparameters are defined using the `hp` object with ranges for integers, floats, and categorical choices.  
- TensorBoard callback tracks training progress and allows visualization of tuning trials.  
- After tuning, the best hyperparameters and trained model can be extracted and saved.

**Model architecture:**  
- Fully connected feed-forward neural network for regression on California Housing data.  
- Input layer sized to number of features (8).  
- Variable number of hidden layers (`0-3`), each with variable neurons (`1-100`) and ReLU activation.  
- Single neuron output layer for continuous target prediction.  
- Mean Squared Error (MSE) as loss, Root Mean Squared Error (RMSE) as metric.

---

## Conclusions

- Hyperparameter tuning via random search and Keras Tuner significantly improves model performance compared to manual tuning.  
- EarlyStopping helps prevent overfitting and reduces training time by halting when validation loss stagnates.  
- Choice of optimizer and learning rate greatly affects training dynamics and final error.  
- TensorBoard integration enables intuitive visualization of tuning process and comparison of trials.  
- Saving best hyperparameters and models ensures reproducibility and allows later deployment or further analysis.

---
