---
title: 'Introduction to Neural Network Mathematics'
description: 'A deep dive into the mathematical foundations of neural networks, including activation functions, loss functions, and backpropagation.'
pubDate: 'Feb 04 2026'
heroImage: '../../assets/blog-placeholder-2.jpg'
---

Neural networks are built on a foundation of mathematical concepts. In this post, we'll explore the key equations that power deep learning.

## Forward Propagation

The basic operation in a neural network layer combines linear transformation with a non-linear activation:

$$
z^{[l]} = W^{[l]} a^{[l-1]} + b^{[l]}
$$

$$
a^{[l]} = g(z^{[l]})
$$

Where $W^{[l]}$ represents the weights, $b^{[l]}$ the biases, and $g$ is the activation function.

## Activation Functions

### Sigmoid

The sigmoid function squashes values between 0 and 1:

$$
\sigma(x) = \frac{1}{1 + e^{-x}}
$$

### ReLU

Rectified Linear Unit, the most popular choice:

$$
\text{ReLU}(x) = \max(0, x)
$$

### Softmax

For multi-class classification, softmax normalizes outputs to a probability distribution:

$$
\text{softmax}(x_i) = \frac{e^{x_i}}{\sum_{j=1}^{K} e^{x_j}}
$$

## Loss Functions

### Cross-Entropy Loss

For classification tasks, we typically use cross-entropy:

$$
\mathcal{L} = -\sum_{i=1}^{n} y_i \log(\hat{y}_i)
$$

### Mean Squared Error

For regression problems:

$$
\text{MSE} = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2
$$

## Gradient Descent

The weights are updated using the gradient of the loss:

$$
W := W - \alpha \frac{\partial \mathcal{L}}{\partial W}
$$

Where $\alpha$ is the learning rate, a crucial hyperparameter.

## Backpropagation

The chain rule allows us to compute gradients through the network:

$$
\frac{\partial \mathcal{L}}{\partial W^{[l]}} = \frac{\partial \mathcal{L}}{\partial a^{[L]}} \cdot \frac{\partial a^{[L]}}{\partial z^{[L]}} \cdot \frac{\partial z^{[L]}}{\partial a^{[L-1]}} \cdots \frac{\partial z^{[l]}}{\partial W^{[l]}}
$$

## Attention Mechanism

The transformer attention formula that revolutionized NLP:

$$
\text{Attention}(Q, K, V) = \text{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right)V
$$

Where $Q$, $K$, and $V$ are the query, key, and value matrices, and $d_k$ is the dimension of the keys.

---

These mathematical foundations are essential for understanding how neural networks learn and make predictions. In future posts, we'll explore more advanced topics like batch normalization, dropout, and optimization algorithms.
