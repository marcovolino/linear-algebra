---
layout: lesson
title: The Graphics Transformation Pipeline
module: 12
lesson: 4
lesson_order: 590
duration_minutes: 45
prerequisites: [Homogeneous transformation matrices, View and projection matrices]
learning_outcomes: [Trace vertices through coordinate spaces., Compose model-view-projection matrices., Transform normals correctly., Diagnose pipeline errors.]
---

## Coordinate Pipeline

A vertex moves through object, world, camera, clip, normalised device, and screen coordinates:

$$
\mathbf{x}_{clip}=PVM\mathbf{x}_{object}.
$$

The combined model-view-projection matrix can transform many vertices efficiently. Perspective division follows, then a viewport transform maps normalised coordinates to pixels.

Normals require special care under non-uniform scaling. Their linear part transforms by

$$
\mathbf{n}'=(A^{-1})^{\mathsf T}\mathbf{n},
$$

followed by normalisation.

```python
import numpy as np

M = np.eye(4)
V = np.eye(4)
P = np.eye(4)
vertices = np.array([[0, 0, 0, 1], [1, 0, 0, 1]], dtype=float)
clip = (P @ V @ M @ vertices.T).T
ndc = clip[:, :3] / clip[:, 3, None]
print(ndc)
```

## Practice

1. List the coordinate spaces in order.
2. Why is perspective division performed after projection?
3. Explain why normals do not always use the model matrix directly.

## Summary

The graphics pipeline is a chain of coordinate changes whose matrix order, conventions, and homogeneous division determine the final screen image.
