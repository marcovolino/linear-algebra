---
layout: lesson
title: Linear Systems and Matrix Form
module: 4
lesson: 1
lesson_order: 130
duration_minutes: 45
prerequisites:
  - Matrices and matrix-vector products
learning_outcomes:
  - Recognise a system of linear equations.
  - Convert between equations and matrix form.
  - Interpret a solution geometrically.
  - Check a proposed solution.
---

## Motivation

Many engineering problems ask for unknown values that satisfy several constraints at once. Circuit currents obey conservation laws, calibration parameters must match observations, and reconstruction methods seek an object consistent with measurements.

## From Equations to Matrices

Consider

$$
\begin{aligned}
2x+y &= 5,\\
x-y &= 1.
\end{aligned}
$$

Collecting coefficients, unknowns, and constants gives

$$
\underbrace{\begin{bmatrix}2&1\\1&-1\end{bmatrix}}_{A}
\underbrace{\begin{bmatrix}x\\y\end{bmatrix}}_{\mathbf{x}}
=
\underbrace{\begin{bmatrix}5\\1\end{bmatrix}}_{\mathbf{b}},
$$

or simply $A\mathbf{x}=\mathbf{b}$. The augmented matrix stores the same information:

$$
\left[
\begin{array}{cc|c}
2&1&5\\
1&-1&1
\end{array}
\right].
$$

## Geometric Meaning

Each equation in two unknowns describes a line. A solution is a point where both lines meet. Two lines may meet once, coincide, or be parallel, corresponding to one, infinitely many, or no solutions.

## Worked Example

The vector $\mathbf{x}=[2,1]^{\mathsf T}$ solves the system because

$$
\begin{bmatrix}2&1\\1&-1\end{bmatrix}
\begin{bmatrix}2\\1\end{bmatrix}
=
\begin{bmatrix}5\\1\end{bmatrix}.
$$

Substitution provides the same check: $2(2)+1=5$ and $2-1=1$.

## Implementation

```python
import numpy as np

A = np.array([[2, 1], [1, -1]])
x = np.array([2, 1])
b = np.array([5, 1])

print(A @ x)
print(np.allclose(A @ x, b))
```

## Practice

1. Write $3x-2y=7$ and $x+4y=6$ as $A\mathbf{x}=\mathbf{b}$.
2. Form the augmented matrix for that system.
3. Check whether $[2,-1]^{\mathsf T}$ is a solution.

## Summary

Matrix form separates a system into coefficients, unknowns, and observations. It gives a compact representation that leads directly to systematic solution methods.
