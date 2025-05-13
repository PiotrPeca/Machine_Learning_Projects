# Lab01 – Introduction to Machine Learning and Data Preparation

## Theoretical Background

**Machine Learning Overview**

* Machine Learning (ML) enables programs to improve performance on a task from experience without explicit programming (Arthur Samuel, 1959; Tom Mitchell, 1997).
* **Supervised** learning uses labeled data (classification, regression); **unsupervised** learning discovers structure without labels (clustering, anomaly detection); **reinforcement** learning optimizes actions via rewards.

**ML Project Workflow**

1. **Data Acquisition:** download and decompress raw datasets programmatically (e.g., using `urllib`, `tarfile`, `gzip`).
2. **Exploratory Data Analysis (EDA):** inspect data structure (`.info()`, `.head()`), summary statistics (`.describe()`), and class/value distributions (`.value_counts()`).
3. **Visualization:** use histograms to understand feature distributions; scatter plots (with size or color encodings) to reveal spatial or bivariate patterns.
4. **Feature Correlation:** compute correlation matrix to identify predictors most strongly related to the target.
5. **Data Splitting:** partition into training and test sets (e.g., 80/20 split) to estimate out-of-sample performance. Random shuffling ensures representativeness.

---

## Conclusions

* **Data Quality:** The California housing dataset contains 20 640 samples with 9 numerical features and 1 categorical (`ocean_proximity`); one feature (`total_bedrooms`) had \~1% missing values.
* **Distribution Insights:** Histograms revealed highly skewed features (e.g., `median_income`, capped `median_house_value`), suggesting potential log transformations or outlier handling.
* **Spatial Patterns:** Scatter plots of longitude vs. latitude colored by price showed higher home values near the coast, confirming geographic influence on housing prices.
* **Key Predictors:** Correlation analysis identified `median_income` as the strongest linear predictor of `median_house_value` (≈ 0.69), while geographic coordinates and population showed weaker or negative correlations.
* **Train/Test Split:** A random 80/20 split produced representative subsets (no missing classes or extreme distribution shifts), suitable for subsequent modeling.
* **Reproducibility:** Saving intermediate results (e.g., `train_set.pkl`, `test_set.pkl`) ensures consistent experiments and easier pipeline deployment.

---
