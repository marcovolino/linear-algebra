---
layout: lesson
title: Diagonalisation
module: 8
lesson: 3
lesson_order: 350
duration_minutes: 50
prerequisites:
  - Eigenpairs
  - Basis and coordinates
learning_outcomes:
  - Explain diagonalisation as a change of basis.
  - Construct A=PDP inverse.
  - Determine when a matrix is diagonalizable.
  - Use diagonalisation to compute powers.
---

## Eigenvector Coordinates

If an $n\times n$ matrix has $n$ independent eigenvectors, place them in

$$
P=\begin{bmatrix}\mathbf{v}_1&\cdots&\mathbf{v}_n\end{bmatrix}
$$

and place their eigenvalues in

$$
D=\operatorname{diag}(\lambda_1,\ldots,\lambda_n).
$$

Then $AP=PD$, so

$$
A=PDP^{-1}.
$$

In the eigenvector basis, the transformation is just coordinate-wise scaling.

## Matrix Powers

Diagonalisation makes repeated application simple:

$$
A^k=PD^kP^{-1},
\qquad
D^k=\operatorname{diag}(\lambda_1^k,\ldots,\lambda_n^k).
$$

## When It Fails

A matrix is diagonalizable exactly when it has enough independent eigenvectors to form a basis. Repeated eigenvalues do not automatically prevent diagonalisation, but a deficient eigenspace does.

## Implementation

```python
import numpy as np

A = np.array([[4, 1], [2, 3]], dtype=float)
values, P = np.linalg.eig(A)
D = np.diag(values)

print(np.allclose(A, P @ D @ np.linalg.inv(P)))
k = 5
print(P @ np.linalg.matrix_power(D, k) @ np.linalg.inv(P))
```

## Practice

1. Diagonalise $\begin{bmatrix}3&0\\0&2\end{bmatrix}$.
2. Use diagonalisation to express $A^{10}$.
3. Explain why a matrix with only one independent eigenvector in $\mathbb{R}^2$ cannot be diagonalised.

## Summary

Diagonalisation changes to an eigenvector basis where a matrix becomes diagonal, making repeated transformations and interpretation much simpler.
