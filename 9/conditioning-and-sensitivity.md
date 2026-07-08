---
layout: lesson
title: Conditioning and Sensitivity
module: 9
lesson: 5
lesson_order: 430
duration_minutes: 45
prerequisites:
  - Singular values
  - Numerical linear systems
learning_outcomes:
  - Define the 2-norm condition number.
  - Interpret ill-conditioning geometrically.
  - Distinguish problem sensitivity from algorithm error.
  - Diagnose conditioning with NumPy.
---

## Condition Number

For a full-rank matrix, the 2-norm condition number is

$$
\kappa_2(A)=\frac{\sigma_{\max}}{\sigma_{\min}}.
$$

A value near $1$ means all directions are scaled similarly. A large value means at least one direction is nearly erased, so recovering it requires strong amplification.

## Sensitivity

Small perturbations in data may cause large changes in the solution of an ill-conditioned system. Roughly,

$$
\frac{\lVert\delta\mathbf{x}\rVert}{\lVert\mathbf{x}\rVert}
\lesssim
\kappa(A)
\frac{\lVert\delta\mathbf{b}\rVert}{\lVert\mathbf{b}\rVert}.
$$

Conditioning belongs to the problem; numerical stability describes how well an algorithm handles that problem.

## Example

```python
import numpy as np

A = np.array([[1.0, 1.0], [1.0, 1.000001]])
b = np.array([2.0, 2.000001])

print("condition number:", np.linalg.cond(A))
print("solution:", np.linalg.solve(A, b))

b_perturbed = b + np.array([0.0, 1e-6])
print("perturbed:", np.linalg.solve(A, b_perturbed))
```

## Regularisation

Truncated SVD and related methods suppress unstable small-singular-value directions. This exchanges some bias for reduced sensitivity to noise.

## Practice

1. Find the condition number of $\operatorname{diag}(10,0.1)$.
2. What does an infinite condition number indicate?
3. Explain why measurement noise matters more in weak singular directions.

## Summary

Singular values quantify sensitivity. A large condition number warns that small data errors can be magnified into large solution errors.
