# Agglomerative Clustering

Agglomerative Clustering is a type of **hierarchical clustering**. It is a bottom-up approach where each data point starts as its own cluster, and pairs of clusters are merged as one moves up the hierarchy. It can be used for both classification and unsupervised learning tasks, like clustering similar data points.

---

## Linkage Methods

The main difference in agglomerative clustering lies in the linkage criterion, which defines how the distance between two clusters is measured. Two popular linkage methods are:

- **Single Linkage**: The distance between two clusters is defined as the shortest distance between any pair of points in the two clusters.
- **Complete Linkage**: The distance between two clusters is defined as the greatest distance between any pair of points in the two clusters.

---

## How Agglomerative Clustering Works

1. **Initialization**: Each data point is initially considered as a single cluster.
2. **Compute Distance**: The distance between each pair of clusters is computed.
3. **Merge Clusters**: The two clusters with the smallest distance are merged.
4. **Repeat**: This process is repeated until all points are in a single cluster or a predefined number of clusters is achieved.

---

## Basic Agglomerative Clustering Usage in Python

Here is the Python code to perform **Agglomerative Clustering** using **Single Linkage** and **Complete Linkage** with the `scikit-learn` library.

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import AgglomerativeClustering
from sklearn.datasets import make_blobs
from scipy.cluster.hierarchy import dendrogram, linkage

# Create a sample dataset
X, _ = make_blobs(n_samples=200, centers=4, cluster_std=0.60, random_state=0)

# Plotting the dataset
plt.scatter(X[:, 0], X[:, 1], s=30)
plt.title("Sample Dataset")
plt.show()

# Agglomerative Clustering using Single Linkage
agg_single = AgglomerativeClustering(n_clusters=4, linkage='single')
y_single = agg_single.fit_predict(X)

# Plotting Single Linkage result
plt.scatter(X[:, 0], X[:, 1], c=y_single, s=30, cmap='viridis')
plt.title("Agglomerative Clustering with Single Linkage")
plt.show()

# Agglomerative Clustering using Complete Linkage
agg_complete = AgglomerativeClustering(n_clusters=4, linkage='complete')
y_complete = agg_complete.fit_predict(X)

# Plotting Complete Linkage result
plt.scatter(X[:, 0], X[:, 1], c=y_complete, s=30, cmap='viridis')
plt.title("Agglomerative Clustering with Complete Linkage")
plt.show()

# Dendrogram for Single Linkage
linked_single = linkage(X, 'single')
plt.figure(figsize=(10, 7))
dendrogram(linked_single)
plt.title("Dendrogram for Single Linkage")
plt.show()

# Dendrogram for Complete Linkage
linked_complete = linkage(X, 'complete')
plt.figure(figsize=(10, 7))
dendrogram(linked_complete)
plt.title("Dendrogram for Complete Linkage")
plt.show()
```


### When to Use Agglomerative Clustering?
When you want to perform hierarchical clustering.

When you have no prior knowledge about the number of clusters.

Suitable for small to medium-sized datasets.

When visualizing the hierarchical structure of data is important (using dendrograms).

---


### Pros and Cons of Agglomerative Clustering
Pros:
No need to predefine the number of clusters (although you can specify it).

Hierarchical nature allows for multi-level analysis.

Can be used for both flat and hierarchical clustering.

Cons:
Computationally expensive (especially for large datasets).

Sensitive to noise and outliers.

May struggle with clusters of varying sizes or densities.

---


### Important Parameters
n_clusters: The number of clusters to form.

linkage: The linkage criterion. Options include 'single', 'complete', 'average', and 'ward'.

affinity: Metric used to compute the linkage. Default is 'euclidean'.

compute_full_tree: If True, the full tree is computed. Default is False.
