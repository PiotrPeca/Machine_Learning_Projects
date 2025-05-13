# Lab08 – PCA and Feature Influence Ranking

## 📝 Description

This lab implements Principal Component Analysis (PCA) on two benchmark datasets and extracts insights on feature importance. The goals are:

* Reduce dimensionality to explain at least 90% of variance.
* Save the explained variance ratios for each selected component.
* Rank original features by their maximum influence on retained components.

---

## 📊 Results Overview

* Breast Cancer dataset: reduced from 30 to *k* components covering ≥90% variance.
* Iris dataset: reduced from 4 to *m* components covering ≥90% variance.
* Feature ranking highlights the most influential measurements (e.g., petal length, mean radius).

---

## 🔍 Notes

* Data are standardized before PCA to ensure equal feature weighting.
* Rankings use absolute loadings weighted by explained variance and select the maximum per feature.
