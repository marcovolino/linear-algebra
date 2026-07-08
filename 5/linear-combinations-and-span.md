---
layout: lesson
title: Linear Combinations and Span
module: 5
lesson: 2
lesson_order: 190
duration_minutes: 45
prerequisites:
  - Vector spaces and subspaces
learning_outcomes:
  - Form linear combinations of vectors.
  - Describe the span of a vector set.
  - Test span membership with a linear system.
  - Interpret span geometrically.
---

## Linear Combinations

A linear combination of vectors $\mathbf{v}_1,\ldots,\mathbf{v}_k$ is

$$
c_1\mathbf{v}_1+\cdots+c_k\mathbf{v}_k.
$$

The span is the set of every such combination:

$$
\operatorname{span}\{\mathbf{v}_1,\ldots,\mathbf{v}_k\}
=
\left\{\sum_{i=1}^{k}c_i\mathbf{v}_i:c_i\in\mathbb{R}\right\}.
$$

The span of one non-zero vector is a line through the origin. Two non-parallel vectors in $\mathbb{R}^3$ span a plane through the origin.

## Membership as a Linear System

To determine whether $\mathbf{b}$ belongs to the span of $\mathbf{v}_1,\ldots,\mathbf{v}_k$, solve

$$
\begin{bmatrix}\mathbf{v}_1&\cdots&\mathbf{v}_k\end{bmatrix}
\mathbf{c}=\mathbf{b}.
$$

A solution for $\mathbf{c}$ proves membership.

## Worked Example

Let

$$
\mathbf{v}_1=\begin{bmatrix}1\\0\\1\end{bmatrix},
\qquad
\mathbf{v}_2=\begin{bmatrix}0\\1\\1\end{bmatrix}.
$$

Then

$$
\begin{bmatrix}2\\3\\5\end{bmatrix}
=2\mathbf{v}_1+3\mathbf{v}_2,
$$

so the vector belongs to their span. Every vector in this span has the form $[a,b,a+b]^{\mathsf T}$.

## Implementation

```python
import numpy as np

V = np.array([[1, 0], [0, 1], [1, 1]], dtype=float)
b = np.array([2, 3, 5], dtype=float)

coefficients, residuals, rank, _ = np.linalg.lstsq(V, b, rcond=None)
print(coefficients)
print(np.allclose(V @ coefficients, b))
```

## Practice

1. Describe the span of $[2,1]^{\mathsf T}$.
2. Is $[1,1,1]^{\mathsf T}$ in the span of $\mathbf{v}_1,\mathbf{v}_2$ above?
3. Find vectors that span the plane $z=2x-y$.

## Summary

Span collects every vector reachable by linear combinations. Testing whether a vector is reachable is equivalent to solving a linear system.
