---
layout: lesson
title: Eigenvalues and Eigenvectors
module: 8
lesson: 1
lesson_order: 330
duration_minutes: 45
prerequisites:
  - Linear transformations
  - Null space
learning_outcomes:
  - Define eigenvalues and eigenvectors.
  - Verify an eigenpair.
  - Interpret eigenvectors geometrically.
  - Distinguish eigenvectors from general vectors.
---

## Invariant Directions

An eigenvector of a square matrix $A$ is a non-zero vector $\mathbf{v}$ satisfying

$$
A\mathbf{v}=\lambda\mathbf{v}.
$$

The scalar $\lambda$ is its eigenvalue. The transformation may stretch, shrink, reverse, or erase the vector, but it does not turn it away from its line.

## Worked Example

For

$$
A=\begin{bmatrix}3&0\\0&2\end{bmatrix},
$$

the standard basis vectors are eigenvectors:

$$
A\mathbf{e}_1=3\mathbf{e}_1,
\qquad
A\mathbf{e}_2=2\mathbf{e}_2.
$$

Most other vectors change direction because their components scale by different amounts.

## Eigenspaces

Rearranging the eigenvalue equation gives

$$
(A-\lambda I)\mathbf{v}=\mathbf{0}.
$$

Thus all eigenvectors associated with $\lambda$, together with zero, form the eigenspace

$$
\operatorname{Null}(A-\lambda I).
$$

## Implementation

```python
import numpy as np

A = np.array([[3, 0], [0, 2]], dtype=float)
values, vectors = np.linalg.eig(A)

for value, vector in zip(values, vectors.T):
    print(value, np.allclose(A @ vector, value * vector))
```

## Applications

Eigenvectors identify principal directions in image data, persistent modes in dynamical systems, and important patterns in graph-based methods.

## Practice

1. Verify that $[1,1]^{\mathsf T}$ is an eigenvector of $\begin{bmatrix}2&1\\1&2\end{bmatrix}$.
2. Find its eigenvalue.
3. Explain why the zero vector is excluded.

## Summary

Eigenvectors are invariant directions of a transformation, and eigenvalues describe the scaling along those directions.
