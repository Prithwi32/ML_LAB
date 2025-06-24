## Linear Discriminant Analysis (LDA)

### What is LDA?

LDA is a **supervised** dimensionality reduction technique used mainly for **classification** problems.

### How LDA works:

- LDA finds a projection that **maximizes the separation (discriminability)** between multiple classes.
- It computes directions (called **linear discriminants**) that maximize the ratio of **between-class variance** to **within-class variance**.
- By projecting data onto these discriminants, it tries to cluster samples of the same class closer and samples of different classes farther apart.

### Use cases of LDA:

- Dimensionality reduction before classification
- Feature extraction for classification problems
- Pattern recognition and face recognition tasks

### Key points:

- LDA is **supervised** — it uses class labels during computation.
- It maximizes **class separability**.
- The maximum number of linear discriminants is `number_of_classes - 1`.

---

## When to Use LDA?
When you have labeled data and want to reduce dimensionality.

To maximize class separability in lower dimensions.

For classification tasks where dimensionality reduction improves performance.

When classes are approximately normally distributed with equal covariance.

## Pros and Cons of LDA
### Pros:

Supervised, so considers class labels.

Often improves classification performance.

Can reduce dimensionality while keeping class discrimination.

### Cons:

Assumes normally distributed features.

Assumes equal covariance matrices for classes.

May not perform well if assumptions are violated.

## Important Parameters
n_components: Number of linear discriminants to keep (<= number of classes - 1).

solver: Algorithm used (svd, lsqr, eigen).

shrinkage: Shrinkage parameter for covariance estimation.

