---
layout: lesson
title: Geometry of the SVD
module: 9
lesson: 2
lesson_order: 400
duration_minutes: 45
prerequisites:
  - Singular values and vectors
  - Linear transformations
learning_outcomes:
  - Interpret each SVD factor geometrically.
  - Describe the image of the unit sphere.
  - Connect zero singular values with null space.
  - Read rank from singular values.
---

## Rotate, Scale, Rotate

In

$$
A=U\Sigma V^{\mathsf T},
$$

$V^{\mathsf T}$ rotates or reflects input coordinates, $\Sigma$ scales perpendicular directions, and $U$ rotates or reflects the result.

The unit circle is mapped to an ellipse whose principal axes are the left singular vectors and whose semi-axis lengths are the singular values.

## Rank and Null Space

The number of positive singular values equals the rank:

$$
\operatorname{rank}(A)=\#\{i:\sigma_i>0\}.
$$

A right singular vector associated with $\sigma_i=0$ belongs to the null space because

$$
A\mathbf{v}_i=0\mathbf{u}_i=\mathbf{0}.
$$

Small singular values describe directions that are nearly erased.

## Numerical Exploration

```python
import numpy as np

A = np.array([[3, 1], [0, 0.5]], dtype=float)
angles = np.linspace(0, 2 * np.pi, 200)
circle = np.vstack((np.cos(angles), np.sin(angles)))
ellipse = A @ circle

U, s, Vt = np.linalg.svd(A)
print("axis lengths:", s)
print("output directions:", U)
```

## Application

In data analysis, large singular values reveal strongly represented directions. Small ones often capture subtle variation or noise, though the interpretation always depends on the application.

## Practice

1. Describe the image of the unit circle under $\operatorname{diag}(5,2)$.
2. What does a zero singular value do geometrically?
3. Explain why rank equals the number of positive singular values.

## Summary

SVD exposes a transformation's principal input and output directions. Singular values quantify how strongly each direction survives.
