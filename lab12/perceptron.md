# Perceptron – Neural Network

## What is a Perceptron?

A **Perceptron** is a simple type of **artificial neural network** used for **binary classification** tasks. It is a **supervised learning** algorithm that classifies input data by learning a linear decision boundary.

## How Perceptron works:

- It takes multiple input features, applies weights to them, and sums them up with a bias.
- The sum is passed through an **activation function** (usually a step function) that outputs either 0 or 1.
- During training, the weights are adjusted based on the error between the predicted and true output using a learning rule.
- After training, the perceptron can classify new inputs by applying the learned weights.

## Use cases of Perceptron:

- Solving simple binary classification problems.
- Implementing basic logical operations like AND, OR.
- Serving as a foundation for more complex neural networks.

## Key points:

- Perceptron is a **single-layer neural network**.
- Can only solve **linearly separable** problems.
- Learns weights iteratively using the perceptron learning rule.
- Output is binary (0 or 1) after applying the activation function.

---

## When to Use Perceptron?

- When your problem is a **binary classification** with linearly separable data.
- To understand the basics of neural networks and machine learning.
- For implementing simple logical functions like AND, OR.
- As a building block before moving to multilayer networks.

---

## Pros and Cons of Perceptron

### Pros:

- Simple to implement and understand.
- Efficient for linearly separable datasets.
- Fast training convergence for simple problems.

### Cons:

- Cannot solve non-linearly separable problems (e.g., XOR).
- Limited to binary classification.
- Requires careful tuning of learning rate and epochs.

---

## Important Parameters

- **input_size**: Number of input features.
- **lr (learning rate)**: Controls the step size during weight updates.
- **epochs**: Number of times the training loop runs over the dataset.

---

## Example Use Cases

- Implementing AND Boolean Function
- Implementing OR Boolean Function
