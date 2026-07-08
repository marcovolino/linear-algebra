---
layout: lesson
title: Basis, Coordinates, and Dimension
module: 5
lesson: 4
lesson_order: 210
duration_minutes: 50
prerequisites:
  - Span
  - Linear independence
learning_outcomes:
  - Determine whether vectors form a basis.
  - Compute coordinates relative to a basis.
  - Define the dimension of a vector space.
  - Interpret a basis as a compact representation.
---

## Basis

A basis for a vector space $V$ is a set of vectors that is both:

- linearly independent;
- spanning for $V$.

Every vector in $V$ then has one unique representation as a linear combination of the basis vectors.

## Coordinates

Let

$$
\mathcal{B}=
\left\{
\begin{bmatrix}1\\1\end{bmatrix},
\begin{bmatrix}1\\-1\end{bmatrix}
\right\}.
$$

To find the coordinates of $\mathbf{x}=[5,1]^{\mathsf T}$ in this basis, solve

$$
c_1\begin{bmatrix}1\\1\end{bmatrix}
+c_2\begin{bmatrix}1\\-1\end{bmatrix}
=\begin{bmatrix}5\\1\end{bmatrix}.
$$

The result is $c_1=3$ and $c_2=2$, so

$$
[\mathbf{x}]_{\mathcal B}=
\begin{bmatrix}3\\2\end{bmatrix}.
$$

## Dimension

The dimension of a vector space is the number of vectors in any basis. For example:

$$
\dim(\mathbb{R}^n)=n,
\qquad
\dim(P_2)=3.
$$

A plane through the origin in $\mathbb{R}^3$ has dimension $2$, even though its vectors have three components.

## Implementation

```python
import numpy as np

B = np.array([[1, 1], [1, -1]], dtype=float)
x = np.array([5, 1], dtype=float)

coordinates = np.linalg.solve(B, x)
reconstructed = B @ coordinates
print(coordinates)
print(np.allclose(reconstructed, x))
```

## Application

A signal represented by hundreds of samples may lie near a low-dimensional subspace. Storing its basis coordinates instead of every sample gives a compact representation, a central idea in compression.

## Practice

1. Does $\{[1,0]^{\mathsf T},[1,1]^{\mathsf T}\}$ form a basis for $\mathbb{R}^2$?
2. Find the coordinates of $[4,2]^{\mathsf T}$ in that basis.
3. Give a basis and dimension for the plane $x+y+z=0$.

## Summary

A basis is a minimal spanning set: enough vectors to reach the whole space, with no redundancy. Dimension counts those independent directions.
