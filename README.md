# Machine Learning Labs – AGH University

This repository contains mini-projects developed as part of the **Machine Learning** course at AGH University of Krakow. Each folder (`labXX`) corresponds to a weekly lab session and is aligned with the content of the respective lecture.

## 🧠 Contents

### 📁 lab01 – Introduction to ML and Data Exploration
- Dataset: California housing data.
- Exploration and visualization using `pandas`, `matplotlib`, `seaborn`.
- Feature correlation analysis.
- Train/test split and basic preprocessing.

### 📁 lab02 – Classification with MNIST
- Dataset: `MNIST` digits.
- Visualization and inspection of individual digits.
- Use of classifiers and evaluation of their performance.
- Metrics: accuracy, confusion matrix, F1 score.

### 📁 lab03 – Regression and Model Comparison
- Custom-generated polynomial data.
- Models: Linear Regression, Polynomial Regression (2–5 degree), and KNN.
- Comparison of models using Mean Squared Error (MSE).
- Results saved with `pickle`.

### 📁 lab04 – Support Vector Machines (SVM)
- Binary and multi-class classification using `SVM`.
- Datasets: breast cancer and iris.
- Data scaling, pipeline construction, and hyperparameter tuning.
- SVM regression task.

### 📁 lab05 – Decision Trees
- Tasks: classification and regression using decision trees.
- Visualization of decision trees with `graphviz`.
- Hyperparameter tuning (max depth).
- Models compared against previous polynomial/KNN regressors.
- Metrics: F1, accuracy, MSE.

### 📁 lab06 – Ensemble Methods
- Ensemble techniques: Voting (hard & soft), Bagging, Pasting, Random Forest, AdaBoost, Gradient Boosting.
- Custom feature and instance sampling strategies.
- Feature importance ranking with decision tree ensembles.
- Metrics tracked for each ensemble model across training and testing sets.

### 📁 lab07 – Unsupervised Learning: Clustering
- Dataset: MNIST-like scanned characters (unknown alphabet).
- K-Means clustering for \(k=8,9,10,11,12\) (selecting the best of 10 runs by inertia), compute silhouette scores, save to `kmeans_sil.pkl`; map clusters to true labels via confusion matrix and save argmax indices to `kmeans_argmax.pkl`.  
- DBSCAN clustering: heuristic search for `eps` based on distances among the first 300 samples, record 10 smallest distances in `dist.pkl`; vary `eps` from \(s\) to \(s+0.1s\) in 0.04s increments, count unique labels for each run and save to `dbscan_len.pkl`.

### 📁 lab08 – PCA and Feature Influence Ranking
- Datasets: Breast Cancer and Iris from scikit-learn.
- Principal Component Analysis to retain 90% of variance (`n_components=0.9`).
- Save explained variance ratios (`.pkl`) and feature influence rankings.
- Implementation of `feature_influence_ranking` using absolute, variance-weighted loadings.

### 📁 lab09 – Neural Networks: Image Classification & Regression
- Classification: Fashion MNIST with a dense neural network (300 & 100-unit hidden layers).
- Regression: California Housing with a dense network and `Normalization` layer.
- Use of callbacks: TensorBoard for logging, EarlyStopping to prevent overfitting.
- Manual train/validation/test split; model saving (`.keras`) and comparison of multiple architectures.

### 📁 lab10 – Hyperparameter Tuning for Neural Networks
- Dataset: California Housing.
- Randomized search over layers, neurons, optimizer and learning rate using `scikeras` + `RandomizedSearchCV`.
- The same search with Keras Tuner, logged to TensorBoard.
- Best hyperparameters (`.pkl`) and best model (`.keras`) saved.

### 📁 lab11 – Image Analysis with CNNs
- Convolutional neural networks for image classification (`tensorflow_datasets`).
- Notebook contains the environment setup only – exercises not completed.

### 📁 lab12 – Time Series Prediction with RNNs
- Dataset: UCI Bike Sharing (hourly rentals, 2011–2012).
- Naive daily/weekly baselines vs. a linear model, LSTM(1), LSTM(32), deep RNN and a multivariate LSTM.
- Metric: MAE on a chronological validation split; results saved with `pickle`, models as `.keras`.

### 📁 lab13 – Autoencoders and Denoising
- Dataset: MNIST.
- Notebook contains data preparation only – autoencoder exercises not completed.
