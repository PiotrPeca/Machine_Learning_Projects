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

### 📁 lab07 – Convolutional Neural Networks
- Dataset: Fashion MNIST (grayscale 28×28 images).
- Dense vs. convolutional architectures: `Dense`, `Conv2D`, `MaxPooling2D`, `Flatten`.
- Activation functions: ReLU, Softmax.
- Data augmentation with `ImageDataGenerator`.
- Training with `sparse_categorical_crossentropy` loss and `Adam` optimizer.
- Visualization of feature maps and training logs in TensorBoard.

### 📁 lab07 – Unsupervised Learning: Clustering
- Dataset: MNIST-like scanned characters (unknown alphabet).
- K-Means clustering for \(k=8,9,10,11,12\) (selecting the best of 10 runs by inertia), compute silhouette scores, save to `kmeans_sil.pkl`; map clusters to true labels via confusion matrix and save argmax indices to `kmeans_argmax.pkl`.  
- DBSCAN clustering: heuristic search for `eps` based on distances among the first 300 samples, record 10 smallest distances in `dist.pkl`; vary `eps` from \(s\) to \(s+0.1s\) in 0.04s increments, count unique labels for each run and save to `dbscan_len.pkl`.

### 📁 lab09 – Neural Networks: Image Classification & Regression
- Classification: Fashion MNIST with a dense neural network (300 & 100-unit hidden layers).
- Regression: California Housing with a dense network and `Normalization` layer.
- Use of callbacks: TensorBoard for logging, EarlyStopping to prevent overfitting.
- Manual train/validation/test split; model saving (`.keras`) and comparison of multiple architectures.
