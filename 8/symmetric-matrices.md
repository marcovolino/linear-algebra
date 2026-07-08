---
layout: lesson
title: Symmetric Matrices
module: 8
lesson: 5
lesson_order: 370
duration_minutes: 45
prerequisites:
  - Eigenvalues and diagonalisation
  - Orthonormal bases
learning_outcomes:
  - Recognise real symmetric matrices.
  - State the spectral theorem.
  - Orthogonally diagonalise a symmetric matrix.
  - Connect symmetric matrices with principal directions.
---

## Symmetry

A real matrix is symmetric when

$$
A^{\mathsf T}=A.
$$

The spectral theorem states that every real symmetric matrix has real eigenvalues and an orthonormal basis of eigenvectors. Therefore

$$
A=QDQ^{\mathsf T},
$$

where $Q$ is orthogonal and $D$ is real and diagonal.

## Worked Example

For

$$
A=\begin{bmatrix}2&1\\1&2\end{bmatrix},
$$

$[1,1]^{\mathsf T}$ has eigenvalue $3$, while $[1,-1]^{\mathsf T}$ has eigenvalue $1$. After normalisation, these eigenvectors form an orthonormal basis.

## Principal Directions

Symmetric matrices appear in quadratic forms, covariance matrices, and graph methods. Their orthogonal eigenvectors identify independent principal directions, while eigenvalues quantify strength or variation along them.

For symmetric numerical problems, use `np.linalg.eigh`; it exploits symmetry and returns real, ordered eigenvalues.

```python
import numpy as np

A = np.array([[2, 1], [1, 2]], dtype=float)
values, Q = np.linalg.eigh(A)
D = np.diag(values)

print(values)
print(np.allclose(Q.T @ Q, np.eye(2)))
print(np.allclose(A, Q @ D @ Q.T))
```

## Practice

1. Verify that the example eigenvectors are orthogonal.
2. Orthogonally diagonalise $\begin{bmatrix}3&0\\0&5\end{bmatrix}$.
3. Explain why symmetric matrices are especially well behaved numerically.

## Summary

Real symmetric matrices have real eigenvalues and orthonormal eigenvectors, giving a stable geometric decomposition into principal directions.
