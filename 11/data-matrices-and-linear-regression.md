---
layout: lesson
title: Data Matrices and Linear Regression
module: 11
lesson: 1
lesson_order: 510
duration_minutes: 50
prerequisites: [Least squares, Rank and conditioning]
learning_outcomes: [Organise samples and features in a matrix., Fit a linear model by least squares., Interpret coefficients and residuals.]
---

## Data and Models

Store $m$ samples with $n$ features as $X\in\mathbb{R}^{m\times n}$. Linear regression predicts

$$
\widehat{\mathbf{y}}=X\boldsymbol{\beta},
\qquad
\widehat{\boldsymbol{\beta}}=\arg\min_{\boldsymbol{\beta}}\lVert X\boldsymbol{\beta}-\mathbf{y}\rVert_2.
$$

Add a column of ones when the model needs an intercept. Standardising features can make coefficient scales and conditioning easier to manage.

```python
import numpy as np

X = np.array([[1, 0], [1, 1], [1, 2], [1, 3]], dtype=float)
y = np.array([1.0, 2.1, 2.9, 4.2])
beta, _, rank, _ = np.linalg.lstsq(X, y, rcond=None)
print(beta, rank, np.linalg.norm(y - X @ beta))
```

## Practice

1. State the shape of a matrix with 500 samples and 12 features.
2. Explain the purpose of an intercept column.
3. What does rank deficiency mean for fitted coefficients?

## Summary

Regression is least squares applied to a data matrix; its columns define features and its residual measures unexplained output.
