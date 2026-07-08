---
layout: lesson
title: Principal Component Analysis
module: 11
lesson: 2
lesson_order: 520
duration_minutes: 50
prerequisites: [Singular value decomposition, Low-rank approximation]
learning_outcomes: [Centre a dataset., Compute principal components using SVD., Reduce and reconstruct data., Interpret explained variance.]
---

## Principal Directions

Centre each feature to form $X_c$. If

$$
X_c=U\Sigma V^{\mathsf T},
$$

the columns of $V$ are principal directions. The reduced coordinates using $k$ components are

$$
Z=X_cV_k,
$$

and reconstruction is $\widehat X=ZV_k^{\mathsf T}+\boldsymbol{\mu}$.

```python
import numpy as np

X = np.array([[1, 2], [2, 3], [3, 5], [4, 6]], dtype=float)
mean = X.mean(axis=0)
U, s, Vt = np.linalg.svd(X - mean, full_matrices=False)
Z = (X - mean) @ Vt[:1].T
reconstruction = Z @ Vt[:1] + mean
explained = s**2 / np.sum(s**2)
print(explained, reconstruction)
```

PCA supports dimensionality reduction and visualisation, but components depend on feature scaling.

## Practice

1. Why must data be centred?
2. State the shape of $Z$ for 100 samples and 3 retained components.
3. How is PCA related to low-rank approximation?

## Summary

PCA uses SVD to find orthogonal directions of greatest sample variation and represent data with fewer coordinates.
