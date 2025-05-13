# Lab03 – Regression

## Theoretical Background

**Linear Regression**

* Models the relationship between input features and a continuous target as a linear function $y = 	heta_0 + 	heta_1 x_1 + \dots + 	heta_n x_n$.
* Parameters $	heta$ are estimated by minimizing the Mean Squared Error (MSE):
  $\mathrm{MSE} = \frac{1}{m} \sum_{i=1}^{m} (\hat y^{(i)} - y^{(i)})^2.$
* Solutions include the Normal Equation $(X^TX)^{-1}X^Ty$ for closed-form or iterative methods like Gradient Descent for large datasets.

**k-Nearest Neighbors Regression (k-NN)**

* Non-parametric: stores all training samples and predicts a new point by averaging the targets of its $k$ nearest neighbors (Euclidean distance).
* No explicit training cost, but prediction is $O(m\log m)$ or $O(m)$ per query depending on data structures.
* Choice of $k$ balances bias and variance: small $k\rightarrow$ low bias, high variance; large $k\rightarrow$ high bias, low variance.

**Polynomial Regression**

* Transforms features into polynomial terms up to degree $d$ (e.g., $x, x^2, ..., x^d$) and applies linear regression in this expanded feature space.
* Captures nonlinear relationships while keeping the model linear in parameters.
* Risk of overfitting increases with degree; regularization or cross-validation recommended for degree selection.

**Model Evaluation**

* Evaluate all models using training and test MSE to assess underfitting or overfitting.
* Compare results side by side (e.g., in a summary table) for clear model selection.

---

## Conclusions

* **Linear Regression** often underfits when the true relationship is nonlinear, evidenced by relatively high MSE on both train and test sets.
* **k-NN Regression:**

  * With $k=3$, the model fits closely to noise (low train MSE, higher test MSE).
  * With $k=5$, smoothing effect improves test MSE at the cost of slightly higher train MSE.
* **Polynomial Regression:**

  * Degree 2–3 provides a good trade-off, capturing the underlying quartic trend with moderate bias and variance.
  * Degrees 4–5 overfit, shown by low train MSE but increased test MSE.
* **Best Model:** Polynomial regression with degree 3 achieved the lowest test MSE, balancing flexibility and generalization.

---
