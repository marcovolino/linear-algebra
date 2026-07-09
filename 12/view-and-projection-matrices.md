---
layout: lesson
title: View and Projection Matrices
module: 12
lesson: 3
lesson_order: 580
duration_minutes: 50
prerequisites: [Homogeneous transformation matrices, Camera projection]
learning_outcomes: [Interpret a view matrix., Distinguish perspective and orthographic projection., Describe clip coordinates., Perform perspective division.]
---

## Camera and Projection

The view matrix $V$ transforms world coordinates into camera coordinates. It is the inverse of the camera's world transform.

The projection matrix $P$ maps camera coordinates into clip coordinates:

$$
\mathbf{x}_{clip}=PV\mathbf{x}_{world}.
$$

Perspective projection makes distant objects smaller. After matrix multiplication, perspective division produces normalised device coordinates:

$$
\mathbf{x}_{ndc}=
\begin{bmatrix}x_c/w_c&y_c/w_c&z_c/w_c\end{bmatrix}^{\mathsf T}.
$$

Orthographic projection does not divide apparent size by depth.

```python
import numpy as np

clip = np.array([2.0, 1.0, 3.0, 4.0])
ndc = clip[:3] / clip[3]
print(ndc)
```

Near and far clipping planes determine the visible depth interval and influence depth-buffer precision.

## Practice

1. Why is the view matrix the inverse camera transform?
2. Compare perspective and orthographic projection.
3. Compute NDC coordinates for $[3,2,1,5]^{\mathsf T}$.

## Summary

View and projection matrices express camera motion and lens behaviour before perspective division maps visible geometry into a standard cube.