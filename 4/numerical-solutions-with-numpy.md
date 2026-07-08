---
layout: lesson
title: Numerical Solutions with NumPy
module: 4
lesson: 4
lesson_order: 160
duration_minutes: 45
prerequisites:
  - Gaussian elimination
  - Solution cases
learning_outcomes:
  - Solve square systems with NumPy.
  - Check residuals and numerical accuracy.
  - Avoid explicit matrix inversion when solving systems.
  - Recognise when least squares is appropriate.
---

## Motivation

Real applications may contain thousands of equations. Numerical libraries implement elimination with pivoting and specialised algorithms that are faster and more reliable than handwritten code.

## Solving a Square System

For an invertible square matrix, use `np.linalg.solve`:

```python
import numpy as np

A = np.array([[3.0, 1.0], [1.0, 2.0]])
b = np.array([9.0, 8.0])

x = np.linalg.solve(A, b)
print(x)
```

This gives $\mathbf{x}=[2,3]^{\mathsf T}$.

{% include callout.html
   type="warning"
   title="Do not form the inverse"
   content="Use solve(A, b), not inv(A) @ b. A direct solve is normally faster, more accurate, and uses less work."
%}

## Checking the Residual

The residual measures how closely the computed solution satisfies the equations:

$$
\mathbf{r}=\mathbf{b}-A\mathbf{x}.
$$

```python
residual = b - A @ x
print(np.linalg.norm(residual))
print(np.allclose(A @ x, b))
```

A small residual is expected, although floating-point results are not always exact.

## Non-Square and Noisy Systems

When measurements produce more equations than unknowns, an exact solution may not exist. `np.linalg.lstsq` finds the vector that minimises the residual norm:

```python
A = np.array([[1.0, 0.0], [1.0, 1.0], [1.0, 2.0]])
b = np.array([1.0, 2.1, 2.9])

x, residuals, rank, singular_values = np.linalg.lstsq(A, b, rcond=None)
print(x)
```

This supports tasks such as fitting a line to noisy measurements. Least squares receives a full geometric treatment later in the course.

## Common Mistakes

- Using integer arrays while implementing elimination that requires division.
- Testing floating-point arrays with exact equality instead of `np.allclose`.
- Ignoring a singular-matrix error rather than examining the system.
- Treating a small residual as proof that a poorly conditioned problem is accurate.

## Practice

1. Solve $2x+y=7$ and $x+3y=11$ with `np.linalg.solve`.
2. Compute the residual norm.
3. Change the second row of $A$ to twice the first and observe the error.

## Summary

Use `np.linalg.solve` for invertible square systems, inspect residuals, and use least squares when noisy data makes an exact solution inappropriate.
