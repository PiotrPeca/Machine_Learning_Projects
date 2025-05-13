# Lab05 – Decision Trees

## 🧠 Theoretical Background

**Decision Trees (CART)**
Classification and regression trees (CART) are nonparametric models that recursively partition the feature space to create a binary tree. At each node, the algorithm selects a feature and threshold that minimizes an impurity measure (Gini impurity or entropy) for classification, or the mean squared error (MSE) for regression.

* **Gini Impurity (classification):**
  $G_i = 1 - \sum_{k=1}^K p_{i,k}^2,$
  where $p_{i,k}$ is the proportion of samples of class $k$ in node $i$.
* **MSE (regression):** selects splits that minimize the weighted average of squared errors in child nodes.

**Key Hyperparameters**

* `max_depth`: maximum tree depth, controls complexity and overfitting.
* `min_samples_split`: minimum samples required to split an internal node.
* `min_samples_leaf`: minimum samples required at a leaf.
* `criterion`: impurity measure (`'gini'` vs `'entropy'` for classification).

**Characteristics**

* **No feature scaling required:** splits are based on thresholds.
* **Interpretability:** the tree can be visualized to show decision rules.
* **Instability:** small changes in data may yield different trees.
* **Bias–Variance Tradeoff:** shallow trees have high bias, deep trees have high variance.

---

## 📝 Conclusions

* **Classification on Breast Cancer dataset:**
  Training and testing F1 scores increased with tree depth up to an optimal `max_depth` (balancing underfitting and overfitting). Beyond that, the training F1 continued to improve while testing F1 plateaued or decreased, indicating overfitting.

* **Tree Visualization:**
  The rendered `bc.png` clearly shows splits based on `mean texture` and `mean symmetry`, making the decision logic transparent.

* **Regression on Synthetic Data:**
  The decision tree regressor approximated the quartic relationship with piecewise constant predictions.

  * Shallow trees underfit (high MSE on both sets).
  * Excessively deep trees overfit the noise (low train MSE, higher test MSE).
  * Optimal depth gave the best compromise, achieving low MSE on both training and test sets.

* **Comparison with Polynomial and KNN Regression:**

  * **Polynomial regression** produced a smooth curve matching the underlying function but required careful degree selection.
  * **KNN regression** yielded a locally smooth but sometimes jagged fit, sensitive to the choice of neighbours.
  * **Decision tree regression** provided a simple, interpretable piecewise model; it was robust to outliers but less smooth than polynomial or KNN predictions.
