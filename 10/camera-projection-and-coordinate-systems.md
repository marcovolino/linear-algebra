---
layout: lesson
title: Camera Projection and Coordinate Systems
module: 10
lesson: 3
lesson_order: 470
duration_minutes: 50
prerequisites:
  - Homogeneous coordinates
  - Matrix composition
learning_outcomes:
  - Describe world, camera, and image coordinates.
  - Apply the pinhole projection model.
  - Interpret intrinsic and extrinsic camera matrices.
  - Project a 3D point into an image.
---

## The Camera Matrix

A homogeneous 3D point $\widetilde{\mathbf{X}}=[X,Y,Z,1]^{\mathsf T}$ maps to a homogeneous image point through

$$
\widetilde{\mathbf{x}}
\sim
P\widetilde{\mathbf{X}},
\qquad
P=K[R\mid\mathbf{t}].
$$

$R$ and $\mathbf{t}$ transform world coordinates into camera coordinates. $K$ contains focal lengths and the principal point.

## Pinhole Projection

For a point in camera coordinates $(X_c,Y_c,Z_c)$,

$$
u=f_x\frac{X_c}{Z_c}+c_x,
\qquad
v=f_y\frac{Y_c}{Z_c}+c_y.
$$

Depth division makes perspective projection non-linear in Cartesian coordinates but linear in homogeneous coordinates before normalisation.

## Implementation

```python
import numpy as np

K = np.array([[800, 0, 320], [0, 800, 240], [0, 0, 1]], dtype=float)
R = np.eye(3)
t = np.zeros((3, 1))
P = K @ np.hstack((R, t))
X = np.array([1, 0.5, 5, 1], dtype=float)

x_h = P @ X
pixel = x_h[:2] / x_h[2]
print(pixel)
```

{% include callout.html
   type="warning"
   title="Coordinate conventions"
   content="Vision libraries differ in axis direction, handedness, and whether transforms map world to camera or camera to world. State conventions before composing matrices."
%}

## Practice

1. Project $(2,1,4)$ using $f_x=f_y=100$ and zero principal point.
2. What happens as depth $Z_c$ increases?
3. State the dimensions of $K$, $[R\mid\mathbf{t}]$, and $P$.

## Summary

Camera projection composes a change of coordinates with an intrinsic mapping, then divides by homogeneous scale to obtain pixel coordinates.
