---
layout: lesson
title: Underdetermined and Overdetermined Systems
module: 6
lesson: 4
lesson_order: 260
duration_minutes: 45
prerequisites:
  - Rank and rank-nullity
  - Numerical solutions with NumPy
learning_outcomes:
  - Distinguish underdetermined and overdetermined systems.
  - Use rank to reason about existence and uniqueness.
  - Interpret redundancy and ambiguity in measurements.
  - Compute least-squares and minimum-norm solutions.
---

## System Shapes

For $A\mathbf{x}=\mathbf{b}$ with $A$ of size $m\times n$:

- $m<n$ is underdetermined: fewer equations than unknowns;
- $m>n$ is overdetermined: more equations than unknowns;
- $m=n$ is square.

Shape alone does not settle the solution count, but it constrains what rank can achieve.

## Underdetermined Systems

Because $\operatorname{rank}(A)\le m<n$, nullity must be positive. If the system is consistent, it has infinitely many solutions. A minimum-norm solution chooses the solution with smallest Euclidean length.

## Overdetermined Systems

An overdetermined system may be inconsistent because noisy measurements need not lie exactly in the column space. Least squares finds

$$
\widehat{\mathbf{x}}
=\arg\min_{\mathbf{x}}\lVert A\mathbf{x}-\mathbf{b}\rVert_2.
$$

Repeated or dependent equations can also be redundant: more measurements do not necessarily increase rank.

## Sensor Example

Suppose columns of $A$ represent unknown source strengths and rows represent sensor readings. A non-trivial null space means some source changes are invisible to every sensor. Dependent rows mean some readings repeat information already supplied by others.

## Implementation

```python
import numpy as np

A = np.array([[1, 0], [1, 1], [1, 2]], dtype=float)
b = np.array([1.0, 2.1, 2.9])

x, residuals, rank, _ = np.linalg.lstsq(A, b, rcond=None)
print("solution:", x)
print("rank:", rank)
print("residual norm:", np.linalg.norm(A @ x - b))

minimum_norm = np.linalg.pinv(A) @ b
```

The pseudoinverse supports least-squares solutions and selects a minimum-norm solution when infinitely many solutions exist.

## Practice

1. Classify the shape of a system with $12$ measurements and $4$ unknowns.
2. Why can such a system still contain redundant measurements?
3. What does a non-trivial null space mean for reconstruction?

## Summary

Underdetermined systems expose ambiguity; overdetermined systems expose consistency and noise. Rank reveals the actual information content beyond the raw number of equations.
