---
layout: lesson
title: QR Decomposition
module: 7
lesson: 4
lesson_order: 310
duration_minutes: 45
prerequisites:
  - Gram-Schmidt
  - Least squares
learning_outcomes:
  - Interpret the factors in A=QR.
  - Connect QR with Gram-Schmidt.
  - Solve least-squares problems using QR.
  - Explain QR's numerical advantage.
---

## Factorisation

For a matrix $A$ with independent columns, a reduced QR decomposition is

$$
A=QR,
$$

where $Q$ has orthonormal columns spanning $\operatorname{Col}(A)$ and $R$ is upper triangular. Gram-Schmidt constructs $Q$ while recording coefficients in $R$.

## Least Squares with QR

Since orthogonal transformations preserve length,

$$
\lVert A\mathbf{x}-\mathbf{b}\rVert_2
=\lVert QR\mathbf{x}-\mathbf{b}\rVert_2.
$$

The least-squares solution satisfies

$$
R\widehat{\mathbf{x}}=Q^{\mathsf T}\mathbf{b}.
$$

This triangular system is solved by back substitution.

## Worked Example

Let

$$
A=\begin{bmatrix}1&1\\1&0\\0&1\end{bmatrix}.
$$

QR produces an orthonormal basis for its column space without changing the model space. The coordinates $Q^{\mathsf T}\mathbf{b}$ express the observation along those stable basis directions.

## Implementation

```python
import numpy as np

A = np.array([[1, 1], [1, 0], [0, 1]], dtype=float)
b = np.array([2, 1, 2], dtype=float)

Q, R = np.linalg.qr(A, mode="reduced")
x = np.linalg.solve(R, Q.T @ b)
print(x)
print(np.linalg.lstsq(A, b, rcond=None)[0])
```

## Numerical Stability

Forming $A^{\mathsf T}A$ amplifies conditioning problems. QR works with orthogonal transformations, which preserve lengths and avoid that unnecessary loss of numerical information.

## Practice

1. State the dimensions of reduced $Q$ and $R$ for a $7\times3$ matrix.
2. Verify $Q^{\mathsf T}Q=I$ and $QR=A$ in NumPy.
3. Solve a least-squares system using QR.

## Summary

QR separates a matrix into orthonormal directions and triangular coordinates, supporting stable least-squares computation.
