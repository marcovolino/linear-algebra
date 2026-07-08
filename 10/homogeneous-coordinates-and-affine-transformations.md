---
layout: lesson
title: Homogeneous Coordinates and Affine Transformations
module: 10
lesson: 2
lesson_order: 460
duration_minutes: 50
prerequisites:
  - Matrix transformations
  - Coordinate systems
learning_outcomes:
  - Convert points to homogeneous coordinates.
  - Represent translation with a matrix.
  - Compose affine transformations.
  - Distinguish points from direction vectors.
---

## Homogeneous Points

A 2D point $(x,y)$ is represented by

$$
\widetilde{\mathbf{x}}=
\begin{bmatrix}x\\y\\1\end{bmatrix}.
$$

Any non-zero scalar multiple represents the same point. Recover Cartesian coordinates by dividing by the final component.

## Affine Transformations

Rotation, scaling, shear, and translation combine in

$$
H=
\begin{bmatrix}
a&b&t_x\\
c&d&t_y\\
0&0&1
\end{bmatrix}.
$$

Then $\widetilde{\mathbf{x}}'=H\widetilde{\mathbf{x}}$. A direction uses final coordinate $0$, so translation does not affect it.

## Composition

If $H_1$ acts first and $H_2$ second, the combined transform is

$$
H=H_2H_1.
$$

Order matters.

## Implementation

```python
import numpy as np

theta = np.deg2rad(30)
rotation = np.array([
    [np.cos(theta), -np.sin(theta), 0],
    [np.sin(theta),  np.cos(theta), 0],
    [0, 0, 1],
])
translation = np.array([[1, 0, 4], [0, 1, 2], [0, 0, 1]])
point = np.array([3, 1, 1])

transformed = translation @ rotation @ point
print(transformed[:2] / transformed[2])
```

## Image Warping

To avoid holes, image warping commonly uses inverse mapping: for each output pixel, apply $H^{-1}$ to find where to sample the input image.

## Practice

1. Write a homogeneous matrix translating by $(5,-2)$.
2. Transform $[1,3,1]^{\mathsf T}$ with it.
3. Explain why a direction has homogeneous coordinate zero.

## Summary

Homogeneous coordinates turn affine geometry into matrix multiplication, allowing transformations and translations to compose in one pipeline.
