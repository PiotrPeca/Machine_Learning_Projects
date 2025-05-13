# Lab02 – Classification

## Theoretical Background

**Data Splitting**

* Splitting into training and test sets must preserve class proportions to ensure representativeness.
* Manual ordered splits (e.g., by label) can yield biased subsets lacking some classes.
* Using `train_test_split(shuffle=True, stratify=y)` randomly distributes samples and maintains class balance.

**Binary Classification with SGDClassifier**

* Stochastic Gradient Descent (SGD) trains a linear model incrementally, suitable for large datasets.
* Predictions are thresholded to produce binary labels.
* Evaluation metrics beyond accuracy include:

  * **Confusion Matrix:** counts true/false positives and negatives.

  * **Precision:** TP/(TP+FP), measures correctness of positive predictions.

  * **Recall:** TP/(TP+FN), measures coverage of actual positives.

  * **F1 Score:** harmonic mean of precision and recall, balances both.
* **Cross-Validation:** `cross_val_score` and `cross_val_predict` provide robust estimates by averaging performance over k folds.

**Multi-class Classification**

* Many classifiers (e.g., SGDClassifier, SVM) are inherently binary.
* **One-vs-Rest (OvR):** trains one binary classifier per class against all others.
* **One-vs-One (OvO):** trains classifiers for each pair of classes; prediction by majority vote.
* Strategies are handled automatically by scikit-learn based on the estimator.

**Error Analysis**

* Normalizing confusion matrices reveals relative error rates across classes.
* Visualization (e.g., heatmaps) helps identify which digits are most often confused.

**Multi-label Classification with KNN**

* Assigns multiple binary labels per sample (e.g., “large digit” and “odd digit”).
* K-Nearest Neighbors predicts each label independently by majority vote among neighbors.

---

## Conclusions

* **Manual vs. Random Splitting:** Ordered splits led to missing classes in training or test sets; random stratified splitting ensures all digits appear in both sets.
* **SGD Binary Classifier ('5' vs. 'not 5'):** Achieved \~95% accuracy, precision \~83.7%, recall \~65.1%, and F1 \~73.3%, highlighting a precision-recall trade-off.
* **Cross-Validation:** 3‑fold CV returned consistent accuracy scores around 95–96%, confirming stability.
* **Multi-class Classification:** SGDClassifier yielded \~87% accuracy across all ten digits; confusion matrix showed common confusions between visually similar digits (e.g., 3 vs. 5).
* **Multi-label Classification:** KNN correctly identified “large” and “odd” properties simultaneously, demonstrating the flexibility of label powerset methods.

---
