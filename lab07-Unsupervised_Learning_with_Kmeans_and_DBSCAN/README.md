## 📋 Clustering Lab Summary

### 📌 KMeans Clustering

In this part of the lab, KMeans clustering was applied to the MNIST dataset using a range of cluster counts from 8 to 12. For each value of `k`, the algorithm was run with `n_init=10` to ensure stable results, and the model with the lowest inertia was selected.

The silhouette score was calculated for each clustering and stored in `kmeans_sil.pkl`. This metric helps evaluate cluster compactness and separation.

Then, the cluster assignments from the KMeans model with `k=10` were compared with the known MNIST labels `y` using a confusion matrix. For each row of this matrix, the index of the highest value was extracted and saved to `kmeans_argmax.pkl`, representing the most likely correspondence between clusters and digit labels.

---

### 📌 DBSCAN Clustering

To find a suitable value for the `eps` parameter in DBSCAN, Euclidean distances were calculated between the first 300 samples and all samples in the dataset. Distances equal to zero (self-distance) were ignored. The 10 smallest distances were sorted and saved to `dist.pkl`.

From the 3 smallest values, the average `s` was computed. Then, a range of `eps` values was generated: from `s` to `s + 10% * s` in steps of `4% * s`. For each value, DBSCAN clustering was applied and the number of unique labels (excluding `-1`, which marks outliers) was recorded and saved to `dbscan_len.pkl`.

### 📊 Comment on DBSCAN Results

The number of detected clusters varied significantly depending on the `eps` value. For instance, the number of clusters for consecutive `eps` values was: **3, 6, and 21**, respectively.

This is expected behavior for DBSCAN, which infers the number of clusters based on the density of points rather than assuming a fixed count. Lower `eps` values detect tight clusters and may classify more points as outliers, while higher `eps` values merge more points into broader clusters.

---

This experiment demonstrates how different clustering algorithms behave under various parameterizations, and how evaluation metrics like silhouette score and domain knowledge (e.g., expected number of digits) can guide model selection.
