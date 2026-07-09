---
layout: lesson
title: Neural Network Layers in Matrix Form
module: 11
lesson: 4
lesson_order: 540
duration_minutes: 45
prerequisites: [Matrix multiplication, Affine transformations]
learning_outcomes: [Express dense layers in matrix form., Track tensor dimensions., Explain the role of bias and activation., Batch multiple samples.]
---

## Affine Layers

A dense layer computes

$$
\mathbf{z}=W\mathbf{x}+\mathbf{b},
\qquad
\mathbf{y}=\phi(\mathbf{z}).
$$

If $W\in\mathbb{R}^{p\times n}$, an $n$-feature input becomes a $p$-feature output. The activation $\phi$ adds non-linearity; without it, any stack of affine layers collapses to one affine transformation.

For row-oriented batches $X\in\mathbb{R}^{m\times n}$:

$$
Z=XW^{\mathsf T}+\mathbf{1}\mathbf{b}^{\mathsf T}.
$$

```python
import numpy as np

X = np.array([[1, 2], [3, 4]], dtype=float)
W = np.array([[1, -1], [0.5, 2]], dtype=float)
b = np.array([0.2, -0.1])
Z = X @ W.T + b
Y = np.maximum(Z, 0)
print(Y)
```

## Practice

1. Track shapes for a batch of 32 samples, 128 inputs, and 64 outputs.
2. Why is an activation needed between layers?
3. Explain bias broadcasting.

## Summary

Neural layers apply familiar affine transformations to batches, then use nonlinear activations to build richer functions.
