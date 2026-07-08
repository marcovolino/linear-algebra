---
layout: lesson
title: Homogeneous Transformation Matrices
module: 12
lesson: 2
lesson_order: 570
duration_minutes: 50
prerequisites: [2D and 3D transformations, Homogeneous coordinates]
learning_outcomes: [Represent 3D translation with matrices., Distinguish points and vectors., Build model matrices., Compose hierarchical transforms.]
---

## 3D Homogeneous Form

A point becomes $[x,y,z,1]^{\mathsf T}$ and a direction becomes $[x,y,z,0]^{\mathsf T}$. An affine transform is

$$
M=
\begin{bmatrix}
a_{11}&a_{12}&a_{13}&t_x\\
a_{21}&a_{22}&a_{23}&t_y\\
a_{31}&a_{32}&a_{33}&t_z\\
0&0&0&1
\end{bmatrix},
$$

where $A$ contains rotation, scale, or shear.

```python
import numpy as np

M = np.eye(4)
M[:3, :3] = np.diag([2, 2, 2])
M[:3, 3] = [3, 0, -1]
point = np.array([1, 2, 3, 1])
direction = np.array([1, 0, 0, 0])
print(M @ point, M @ direction)
```

Model matrices move object coordinates into world coordinates. In a hierarchy, a child transform is composed with its parent's world transform.

## Practice

1. Build a translation by $(2,-1,5)$.
2. Show that it does not translate a direction.
3. Explain transformation order in a parent-child model.

## Summary

Homogeneous matrices unify linear transformations and translation, enabling model placement and hierarchical animation.
