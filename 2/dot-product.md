---
layout: lesson
title: Dot Product
module: 2
lesson: 3
lesson_order: 40
duration_minutes: 40
prerequisites:
  - Vectors
  - Vector operations
learning_outcomes:
  - Compute the dot product of two vectors.
  - Relate the dot product to alignment and angle.
  - Use the dot product to measure similarity.
  - Implement dot products with NumPy.
---

## Motivation

The dot product turns two vectors into one number. That number tells us how strongly the vectors point in the same direction. This makes the dot product useful for lighting in graphics, similarity in machine learning, and signal comparison in engineering.

{% include callout.html
   type="application"
   title="Graphics connection"
   content="A simple diffuse lighting model uses a dot product between a surface normal and a light direction. If the vectors point in similar directions, the surface is bright; if they are perpendicular, it receives little direct light."
%}

## Definition

For two vectors in $\mathbb{R}^N$,

$$
\mathbf{v} =
\begin{bmatrix}
v_1 \\
v_2 \\
\vdots \\
v_N
\end{bmatrix},
\qquad
\mathbf{w} =
\begin{bmatrix}
w_1 \\
w_2 \\
\vdots \\
w_N
\end{bmatrix},
$$

the dot product is

$$
\mathbf{v}\cdot\mathbf{w}
=
\sum_{n=1}^{N} v_n w_n
=
v_1w_1 + v_2w_2 + \dots + v_Nw_N.
$$

Both vectors must have the same number of components.

## Geometric Meaning

The dot product is also related to the angle $\theta$ between two non-zero vectors:

$$
\mathbf{v}\cdot\mathbf{w}
=
\lVert \mathbf{v} \rVert_2
\lVert \mathbf{w} \rVert_2
\cos\theta.
$$

This gives three important cases:

- If $\mathbf{v}\cdot\mathbf{w} > 0$, the angle is acute and the vectors point broadly in the same direction.
- If $\mathbf{v}\cdot\mathbf{w} = 0$, the vectors are orthogonal.
- If $\mathbf{v}\cdot\mathbf{w} < 0$, the angle is obtuse and the vectors point broadly in opposite directions.

<script type="text/tikz">
\begin{tikzpicture}
\draw[help lines, color=gray!25, dashed] (-.2,-.2) grid (4.2,3.2);
\draw[->,thick] (0,0)--(4.5,0) node[right]{$x$};
\draw[->,thick] (0,0)--(0,3.5) node[above]{$y$};
\draw[->,ultra thick, blue] (0,0)--(4,1) node[right]{$\mathbf{v}$};
\draw[->,ultra thick, teal] (0,0)--(2,3) node[above]{$\mathbf{w}$};
\draw (0.9,0.22) arc[start angle=14,end angle=56,radius=.95];
\node at (1.25,.62) {$\theta$};
\end{tikzpicture}
</script>

## Worked Example

Let

$$
\mathbf{v} =
\begin{bmatrix}
2 \\
1 \\
3
\end{bmatrix},
\qquad
\mathbf{w} =
\begin{bmatrix}
4 \\
-2 \\
1
\end{bmatrix}.
$$

Then

$$
\mathbf{v}\cdot\mathbf{w}
= 2(4) + 1(-2) + 3(1)
= 8 - 2 + 3
= 9.
$$

The positive result means the vectors point more in the same direction than in opposite directions.

## Implementation

```python
import numpy as np

v = np.array([2, 1, 3])
w = np.array([4, -2, 1])

print(np.dot(v, w))
print(v @ w)
```

## Common Mistakes

- Multiplying only the first components and forgetting the sum.
- Computing a dot product between vectors of different lengths.
- Assuming a large dot product always means high similarity. Vector length also affects the result, which is why cosine similarity is often used.

## Practice

1. Compute $[1,2]^{\mathsf T}\cdot[3,4]^{\mathsf T}$.
2. Compute $[2,-1,0]^{\mathsf T}\cdot[1,4,5]^{\mathsf T}$.
3. Find a non-zero vector that is orthogonal to $[2,1]^{\mathsf T}$.

## Summary

The dot product combines component-wise multiplication with summation. It measures alignment, supports angle calculations, and becomes a core building block for projections, similarity, matrix multiplication, and least squares.
