---
layout: lesson
title: Null Space
module: 6
lesson: 2
lesson_order: 240
duration_minutes: 45
prerequisites:
  - Homogeneous systems
  - Basis and dimension
learning_outcomes:
  - Define the null space of a matrix.
  - Find a null-space basis by row reduction.
  - Interpret null vectors as invisible input directions.
  - Connect null space with solution ambiguity.
---

## Definition

The null space of an $m\times n$ matrix is

$$
\operatorname{Null}(A)
=
\{\mathbf{x}\in\mathbb{R}^n:A\mathbf{x}=\mathbf{0}\}.
$$

It is a subspace of the input space $\mathbb{R}^n$.

## Worked Example

For

$$
A=\begin{bmatrix}1&2&-1\\2&4&-2\end{bmatrix},
$$

the equation $A\mathbf{x}=\mathbf{0}$ reduces to

$$
x_1+2x_2-x_3=0.
$$

Let $x_2=s$ and $x_3=t$. Then $x_1=-2s+t$, so

$$
\mathbf{x}
=s\begin{bmatrix}-2\\1\\0\end{bmatrix}
+t\begin{bmatrix}1\\0\\1\end{bmatrix}.
$$

These two vectors form a basis for $\operatorname{Null}(A)$.

## Geometric Meaning

Null vectors are input changes that produce no output. If $A\mathbf{x}_1=A\mathbf{x}_2$, then

$$
A(\mathbf{x}_1-\mathbf{x}_2)=\mathbf{0},
$$

so the two inputs differ by a null-space vector.

In reconstruction, a non-trivial null space represents ambiguity: distinct objects can produce identical measurements.

## Implementation

```python
import numpy as np

A = np.array([[1, 2, -1], [2, 4, -2]], dtype=float)
_, singular_values, Vt = np.linalg.svd(A)
tolerance = 1e-10
rank = np.sum(singular_values > tolerance)
null_basis = Vt[rank:].T

print(null_basis)
print(np.allclose(A @ null_basis, 0))
```

## Practice

1. Find a basis for the null space of $\begin{bmatrix}1&1&1\end{bmatrix}$.
2. What is the null space of the identity matrix?
3. Explain why a non-zero null vector prevents a transformation from being one-to-one.

## Summary

The null space contains inputs erased by a transformation. Its dimension measures the number of independent invisible directions.
