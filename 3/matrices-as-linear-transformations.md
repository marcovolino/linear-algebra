---
layout: lesson
title: Matrices as Linear Transformations
module: 3
lesson: 4
lesson_order: 110
duration_minutes: 50
prerequisites:
  - Matrix-vector products
  - Matrix multiplication
learning_outcomes:
  - Interpret a matrix as a function from vectors to vectors.
  - Describe scaling, shear, reflection, and rotation matrices.
  - Connect matrix columns to transformed basis vectors.
  - Implement simple 2D transformations in NumPy.
---

## Motivation

A matrix is more than a table of numbers. It can act like a machine that takes a vector in and returns a new vector out. This viewpoint is central to graphics, robotics, computer vision, and neural networks.

{% include callout.html
   type="application"
   title="Computer graphics connection"
   content="A 2D object is often stored as a list of points. Multiplying every point by a transformation matrix can rotate, scale, shear, or reflect the whole object."
%}

## Matrices as Functions

A matrix $A$ defines a function

$$
\mathbf{x}
\mapsto
A\mathbf{x}.
$$

If $A$ is $m \times n$, then it maps vectors from $\mathbb{R}^n$ to vectors in $\mathbb{R}^m$:

$$
A:\mathbb{R}^n \to \mathbb{R}^m.
$$

## Columns Show Where Basis Vectors Go

In two dimensions, the standard basis vectors are

$$
\mathbf{e}_1 =
\begin{bmatrix}
1 \\
0
\end{bmatrix},
\qquad
\mathbf{e}_2 =
\begin{bmatrix}
0 \\
1
\end{bmatrix}.
$$

For

$$
A =
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix},
$$

the columns of $A$ are the transformed basis vectors:

$$
A\mathbf{e}_1 =
\begin{bmatrix}
a \\
c
\end{bmatrix},
\qquad
A\mathbf{e}_2 =
\begin{bmatrix}
b \\
d
\end{bmatrix}.
$$

This is the geometric heart of matrix transformations.

## Common 2D Transformations

Scaling:

$$
\begin{bmatrix}
s_x & 0 \\
0 & s_y
\end{bmatrix}.
$$

Reflection in the $x$-axis:

$$
\begin{bmatrix}
1 & 0 \\
0 & -1
\end{bmatrix}.
$$

Shear in the $x$ direction:

$$
\begin{bmatrix}
1 & k \\
0 & 1
\end{bmatrix}.
$$

Rotation by angle $\theta$:

$$
R(\theta)
=
\begin{bmatrix}
\cos\theta & -\sin\theta \\
\sin\theta & \cos\theta
\end{bmatrix}.
$$

## Geometric Example

The matrix

$$
A =
\begin{bmatrix}
2 & 0 \\
0 & 1
\end{bmatrix}
$$

stretches vectors horizontally by a factor of $2$ while leaving the vertical coordinate unchanged.

<script type="text/tikz">
\begin{tikzpicture}
\draw[help lines, color=gray!25, dashed] (-.2,-.2) grid (5.2,3.2);
\draw[->,thick] (0,0)--(5.5,0) node[right]{$x$};
\draw[->,thick] (0,0)--(0,3.5) node[above]{$y$};
\draw[->,ultra thick, blue] (0,0)--(2,2) node[above left]{$\mathbf{x}$};
\draw[->,ultra thick, purple] (0,0)--(4,2) node[right]{$A\mathbf{x}$};
\draw[dashed] (2,2)--(4,2);
\end{tikzpicture}
</script>

## Implementation

```python
import numpy as np

points = np.array([
    [0, 0],
    [1, 0],
    [1, 1],
    [0, 1],
])

scale = np.array([[2, 0], [0, 1]])
transformed = points @ scale.T

print(transformed)
```

The transpose appears in `points @ scale.T` because each point is stored as a row. If points were stored as column vectors, the expression would be `scale @ point`.

## Common Mistakes

- Forgetting whether vectors are stored as rows or columns in code.
- Applying transformations in the wrong order.
- Treating translation as a $2 \times 2$ linear transformation. Translation requires homogeneous coordinates, which appear later in graphics and vision.

## Practice

1. What does $\begin{bmatrix}3 & 0 \\ 0 & 3\end{bmatrix}$ do to a 2D point?
2. What happens to $\mathbf{e}_1$ and $\mathbf{e}_2$ under $\begin{bmatrix}1 & 2 \\ 0 & 1\end{bmatrix}$?
3. Write the rotation matrix for $\theta=90^\circ$.

## Summary

Matrix columns show where basis vectors are sent. This makes a matrix a compact description of a geometric transformation, and matrix multiplication composes transformations.
