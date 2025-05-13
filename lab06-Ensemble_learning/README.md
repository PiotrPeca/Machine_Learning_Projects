# Lab06 – Ensemble Methods

## 🧠 Theoretical Background

**Voting (Hard & Soft)**
Combines predictions from multiple classifiers by majority vote (hard) or averaging predicted probabilities (soft). Soft voting often yields smoother decision boundaries when classifiers provide reliable probability estimates.

**Bagging vs. Pasting**

* *Bagging* (bootstrap aggregating): trains each estimator on a random subset of training instances with replacement; reduces variance.
* *Pasting*: same as bagging but without replacement; useful when overfitting is less severe.

**Random Forest**
An extension of bagging applied to decision trees: each tree is trained on a bootstrap sample and at each split considers a random subset of features. This decorrelates trees and typically boosts generalization performance compared to plain bagging of trees.

**Boosting (AdaBoost & Gradient Boosting)**

* *AdaBoost*: sequentially trains weak learners, reweighting samples to emphasize those misclassified; final prediction is a weighted vote of learners.
* *Gradient Boosting*: sequentially fits new learners to the residual errors of the ensemble, optimizing a differentiable loss via gradient descent in function space.

**Feature Sampling & Ranking**
Sampling subsets of features for each base learner (random subspaces) can improve robustness and highlight the most informative features. By evaluating individual estimators’ performance and their chosen feature subsets, one can rank features by their contribution to accuracy.

---

## 📝 Conclusions

* **Voting ensembles** consistently outperformed individual models; soft voting yielded a slight edge when probability estimates were available.
* **Bagging** of decision trees reduced variance and improved stability; pasting showed similar trends but with marginally higher bias.
* **Random Forest** delivered better generalization than plain bagging thanks to random feature selection at splits, reducing correlation among trees.
* **Boosting methods** achieved the highest accuracy on training data, with AdaBoost being simpler to tune and Gradient Boosting offering finer control via learning rate and loss functions.
* **Feature sampling** experiments revealed that certain feature subsets led to superior performance; the ranking procedure identified the most predictive features, guiding future feature engineering.
