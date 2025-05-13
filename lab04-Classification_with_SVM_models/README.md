# Lab04 – Support Vector Machines

## Theoretical Background

**Support Vector Machine (SVM) Classification**

* **Hard Margin SVM:** Searches for the maximum-margin linear decision boundary when the data are perfectly separable.
* **Soft Margin SVM:** Introduces the regularization parameter `C` to balance margin width and classification errors. A lower `C` allows a wider margin with more misclassifications (reducing overfitting), while a higher `C` favors a narrower margin with fewer misclassifications (increasing fitting power).
* **Feature Scaling:** SVMs are sensitive to feature scales. Applying `StandardScaler` before training ensures all features contribute proportionally to the margin.

**Kernel Trick & Nonlinear Decision Boundaries**

* **Polynomial Feature Expansion vs. Kernel:** Explicitly transforming features with `PolynomialFeatures` increases dimensionality, while `SVC(kernel="poly")` uses the polynomial kernel to compute dot products in the higher-dimensional space more efficiently without creating all polynomial features.
* **Polynomial Kernel Parameters:** `degree` (polynomial degree), `coef0` (independent term), and `C` (regularization) control the shape and flexibility of the decision boundary.

**Hyperparameter Search**

* **GridSearchCV:** Exhaustively tests specified parameter grids and evaluates performance using metrics like `accuracy` for classification or `neg_mean_squared_error` for regression.
* **RandomizedSearchCV:** Samples a fixed number of parameter combinations randomly, which can be more efficient when the search space is large.
* **Pipeline Parameter Naming:** Use the syntax `<step_name>__<parameter_name>` to reference parameters within scikit-learn pipelines.

**SVM Regression**

* **LinearSVR:** Implements linear support vector regression with an ε-insensitive loss. The `epsilon` parameter defines the width of the insensitive tube, and `C` controls regularization strength.
* **Kernel SVR:** Allows nonlinear regression by applying kernels (e.g., `kernel="poly"` for polynomial relationships).

---

## Conclusions

* **Breast Cancer Classification:**

  * Without feature scaling, test accuracy drops significantly.
  * After scaling, accuracy improves due to balanced feature contributions.

* **Iris Classification (Virginica vs. Others):**

  * Scaling benefits remain clear.
  * `LinearSVC` separates classes well using petal measurements.

* **Nonlinear Classification on the Two Moons Dataset:**

  * A `Pipeline` with `PolynomialFeatures(degree=3)` and `LinearSVC` successfully separates the two moon shapes.
  * Using `SVC(kernel="poly")` proved more efficient at higher degrees and simplified the workflow.

* **Hyperparameter Tuning:**

  * For `SVC`, high values of `C` (e.g., 1000) and polynomial degrees of 4 or 5 yielded the best results.
  * `RandomizedSearchCV` achieved comparable accuracy with fewer parameter evaluations.

* **LinearSVR Regression:**

  * Proper tuning of `epsilon` achieved low MSE on both training and test sets, comparable to polynomial regression.

* **Nonlinear SVR (Polynomial Degree=4):**

  * Default hyperparameters produced high MSE.
  * Applying `GridSearchCV` to optimize `C` and `coef0` significantly improved model performance.

---
