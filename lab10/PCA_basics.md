# PCA (Principal Component Analysis)

### What is PCA?

PCA is an **unsupervised** statistical technique used to reduce the dimensionality of a dataset while preserving as much variance (information) as possible.

### How PCA works:

- PCA identifies directions (called **principal components**) in which the data varies the most.
- These components are orthogonal (uncorrelated) to each other.
- The data is then projected onto the top principal components, reducing the number of features.
- Typically, the first few principal components capture the majority of the data variance.

### Use cases of PCA:

- Data visualization (2D or 3D projection of high-dimensional data)
- Noise reduction
- Speeding up machine learning algorithms by reducing features
- Finding latent patterns in data

### Key points:

- PCA is **unsupervised** — it does not use class labels.
- It maximizes **variance** in the projected space.
- Components are linear combinations of original features.

## Pros and Cons of PCA
### Pros:

Reduces overfitting by removing noise and redundant features.

Speeds up training and visualization.

Unsupervised and does not require labels.

### Cons:

Principal components may be hard to interpret.

Assumes linear relationships.

Sensitive to scaling of features (requires standardization).

## Important Parameters
n_components: Number of principal components to keep.

whiten: Whether to whiten components (decorrelate and normalize).

svd_solver: Algorithm to use for decomposition (auto, full, randomized).

---

## Differences between PCA and LDA

| Feature               | PCA                           | LDA                           |
|-----------------------|-------------------------------|-------------------------------|
| Type                  | Unsupervised                  | Supervised                    |
| Objective             | Maximize variance            | Maximize class separability  |
| Use of labels         | No                           | Yes                          |
| Number of components  | <= number of original features | <= number of classes - 1     |
| Application           | General dimensionality reduction | Classification and feature extraction |

---

## Summary

- **PCA** reduces dimensionality by projecting data onto directions of highest variance without considering class labels. Useful for visualization and noise reduction.
- **LDA** reduces dimensionality by projecting data onto directions that best separate the classes, leveraging class labels, mainly useful before classification.

---

## References

- [Principal Component Analysis - GFG](https://www.geeksforgeeks.org/principal-component-analysis-pca)
- [Linear Discriminant Analysis - GFG](https://www.geeksforgeeks.org/machine-learning/ml-linear-discriminant-analysis)
- [scikit-learn PCA documentation](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html)
- [scikit-learn LDA documentation](https://scikit-learn.org/stable/modules/generated/sklearn.discriminant_analysis.LinearDiscriminantAnalysis.html)

