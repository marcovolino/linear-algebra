---
layout: lesson
title: 2D and 3D Transformations
module: 12
lesson: 1
lesson_order: 560
duration_minutes: 45
prerequisites: [Matrices as linear transformations, Homogeneous coordinates]
learning_outcomes: [Construct scale and rotation matrices., Transform points and directions., Compose transformations., Recognise coordinate conventions.]
---

## Core Transformations

In 2D,

$$
R(\theta)=
\begin{bmatrix}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{bmatrix}.
$$

In 3D, rotations occur about coordinate axes. Scaling uses a diagonal matrix. Matrix multiplication composes operations, with the rightmost transform acting first for column vectors.

```python
import numpy as np

theta = np.deg2rad(45)
R = np.array([[np.cos(theta), -np.sin(theta)],
              [np.sin(theta),  np.cos(theta)]])
S = np.diag([2.0, 0.5])
point = np.array([1.0, 1.0])
print(R @ S @ point)
```

Graphics APIs may use row vectors, column vectors, left-handed, or right-handed coordinates. Consistency matters more than the chosen convention.

## Practice

1. Build a reflection in the $x$-axis.
2. Compare rotate-then-scale with scale-then-rotate.
3. Verify a rotation preserves length.

## Summary

Graphics transforms use matrices to move geometric data between frames while composition builds complex motion from simple operations.
