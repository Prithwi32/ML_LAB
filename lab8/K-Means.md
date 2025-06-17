# K-Means Clustering

K-Means is an unsupervised machine learning algorithm used for clustering data into groups based on feature similarity. It partitions data into `k` clusters by minimizing the variance within each cluster.

---

## What is K-Means?

K-Means aims to divide `n` observations into `k` clusters where each observation belongs to the cluster with the nearest mean (centroid), serving as a prototype of the cluster.

---

## How K-Means Works

1. Choose the number of clusters, `k`.
2. Initialize `k` centroids randomly.
3. Assign each data point to the nearest centroid based on a distance metric (usually Euclidean distance).
4. Update centroids by calculating the mean of all points assigned to each cluster.
5. Repeat steps 3 and 4 until centroids no longer change significantly or a maximum number of iterations is reached.

---

## Basic K-Means Usage in Python

```python
from sklearn.cluster import KMeans
import numpy as np

# Example dataset (X = features)
X = np.array([[1, 2], [1, 4], [1, 0],
              [4, 2], [4, 4], [4, 0]])

# Create KMeans object with k=2 clusters
kmeans = KMeans(n_clusters=2, random_state=0)

# Fit the model and predict cluster labels
labels = kmeans.fit_predict(X)

# Cluster centroids
centroids = kmeans.cluster_centers_

print("Cluster labels:", labels)
print("Centroids:", centroids)
```

## Important Parameters
n_clusters: Number of clusters to form.

init: Method for initialization ('k-means++' is default and preferred).

n_init: Number of time the k-means algorithm will be run with different centroid seeds.

max_iter: Maximum number of iterations for a single run.

random_state: Seed used by the random number generator for reproducibility.

## When to Use K-Means?
When you want to group data points without pre-existing labels (unsupervised).

When clusters are expected to be spherical and roughly equal size.

For exploratory data analysis to find hidden patterns or groupings.

When you have medium-sized datasets (K-Means scales well with data size).

## Pros and Cons
### Pros:

Simple and easy to implement.

Efficient and scalable to large datasets.

Works well when clusters are compact and well-separated.

### Cons:

Requires specifying the number of clusters k upfront.

Sensitive to initial centroid placement.

Assumes clusters are convex and isotropic (e.g., spherical).

Can be affected by outliers and noise.

Not suitable for discovering clusters of complex shapes.

## Additional Notes
Feature scaling (standardization or normalization) is important because K-Means uses distance metrics.

The elbow method is commonly used to help choose the optimal number of clusters k.

Variants and extensions include MiniBatchKMeans for faster clustering on large datasets.
