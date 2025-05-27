# K-Nearest Neighbors (KNN) Classifier

K-Nearest Neighbors (KNN) is a simple, yet powerful supervised machine learning algorithm used for classification and regression tasks. It classifies a data point based on how its neighbors are classified.

---

## What is KNN?

KNN works by finding the 'k' closest data points (neighbors) to the point you want to classify, then assigning the class that is most common among those neighbors. The closeness is usually measured using distance metrics like Euclidean or Manhattan distance.

---

## How KNN Works

1. Choose the number of neighbors, `k`.
2. Calculate the distance between the new data point and all training data points.
3. Select the `k` nearest neighbors based on the distance.
4. Assign the most frequent class label among these neighbors to the new point.

---


## Basic KNN Usage in Python

```python
from sklearn.neighbors import KNeighborsClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

# Example dataset (X = features, y = target labels)
X = [[1, 2], [2, 3], [3, 4], [6, 7], [7, 8], [8, 9]]
y = [0, 0, 0, 1, 1, 1]

# Split data into training and testing
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

# Create KNN model with k=3 neighbors
knn = KNeighborsClassifier(n_neighbors=3)

# Train the model
knn.fit(X_train, y_train)

# Predict on test data
y_pred = knn.predict(X_test)

# Evaluate accuracy
print("Accuracy:", accuracy_score(y_test, y_pred))
```


### Important Parameters
n_neighbors: Number of neighbors to use (k).

metric: Distance metric to use ('euclidean', 'manhattan', etc.).

weights: Weight function used in prediction ('uniform' or 'distance').

algorithm: Algorithm used to compute the nearest neighbors ('auto', 'ball_tree', 'kd_tree', 'brute').


### When to Use KNN?
When you have labeled data for classification or regression.

When you want a simple and interpretable model.

For small to medium-sized datasets (KNN can be slow with large datasets).

When decision boundaries are irregular or nonlinear.

When feature scaling has been applied (KNN is sensitive to feature scales).



### Pros and Cons
Pros:

Easy to understand and implement.

No assumptions about data distribution (non-parametric).

Naturally handles multi-class classification.

Can be used for classification and regression.



### Cons:

Computationally expensive during prediction (lazy learner).

Performance degrades with high-dimensional data (curse of dimensionality).

Sensitive to irrelevant or redundant features.

Requires careful choice of k and distance metric.

Sensitive to feature scaling and noise.


