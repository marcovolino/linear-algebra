---
layout: lesson
title: Gram-Schmidt and Orthogonal Matrices
module: 7
lesson: 2
lesson_order: 290
duration_minutes: 50
prerequisites:
  - Orthogonal projections
  - Linear independence
learning_outcomes:
  - Apply the Gram-Schmidt process.
  - Preserve span while constructing an orthonormal basis.
  - Recognise orthogonal matrices.
  - Explain why orthogonal transformations preserve length.
---

## Gram-Schmidt

Given independent vectors $\mathbf{v}_1,\ldots,\mathbf{v}_k$, set

$$
\mathbf{u}_1=\mathbf{v}_1,
\qquad
\mathbf{u}_j=\mathbf{v}_j-\sum_{i=1}^{j-1}
\operatorname{proj}_{\mathbf{u}_i}(\mathbf{v}_j),
$$

then normalise each $\mathbf{u}_j$ to obtain $\mathbf{q}_j$.

## Worked Example

For $\mathbf{v}_1=[1,1]^{\mathsf T}$ and $\mathbf{v}_2=[1,0]^{\mathsf T}$,

$$
\mathbf{q}_1=\frac{1}{\sqrt2}\begin{bmatrix}1\\1\end{bmatrix}.
$$

Removing the component of $\mathbf{v}_2$ along $\mathbf{q}_1$ gives

$$
\mathbf{u}_2
=\begin{bmatrix}1\\0\end{bmatrix}
-\frac12\begin{bmatrix}1\\1\end{bmatrix}
=\frac12\begin{bmatrix}1\\-1\end{bmatrix},
$$

so $\mathbf{q}_2=2^{-1/2}[1,-1]^{\mathsf T}$.

## Orthogonal Matrices

A square matrix $Q$ is orthogonal when

$$
Q^{\mathsf T}Q=I,
\qquad
Q^{-1}=Q^{\mathsf T}.
$$

It preserves dot products, lengths, and angles:

$$
\lVert Q\mathbf{x}\rVert_2=\lVert\mathbf{x}\rVert_2.
$$

Rotations and reflections are orthogonal transformations.

## Implementation

```python
import numpy as np

A = np.array([[1, 1], [1, 0]], dtype=float)
Q, R = np.linalg.qr(A)
print(Q)
print(np.allclose(Q.T @ Q, np.eye(2)))
```

## Practice

1. Apply Gram-Schmidt to $[1,0,1]^{\mathsf T}$ and $[1,1,0]^{\mathsf T}$.
2. Verify that a $90^\circ$ rotation matrix is orthogonal.
3. Explain why orthogonal matrices are numerically attractive.

## Summary

Gram-Schmidt replaces an independent set with an orthonormal basis for the same span. Orthogonal matrices built from such bases preserve geometry.
