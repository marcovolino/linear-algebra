---
layout: lesson
title: Vector Operations
module: 2
lesson: 2
lesson_order: 30
duration_minutes: 35
prerequisites:
  - Vectors
  - Vector magnitude
learning_outcomes:
  - Add and subtract vectors component by component.
  - Multiply a vector by a scalar.
  - Interpret vector operations geometrically.
  - Form linear combinations of vectors.
---

## Motivation

Vector operations let us combine measurements, move points, compare directions, and build new representations from existing ones. In graphics, vector addition can move an object. In data science, scalar multiplication can rescale a feature vector.

## Addition and Subtraction

Vectors are added and subtracted component by component:

$$
\mathbf{v} \pm \mathbf{w}  = \begin{bmatrix}
v_1 \pm w_1 \\
v_2 \pm w_2 \\
\vdots \\
v_N \pm w_N
\end{bmatrix}
$$

- Vector addition is commutative: $\mathbf{v} + \mathbf{w} = \mathbf{w} + \mathbf{v}$.
- Vector subtraction is not commutative: $\mathbf{v} - \mathbf{w} \neq \mathbf{w} - \mathbf{v}$ in general.

## Worked Example

$$
\begin{bmatrix}
1 \\
2
\end{bmatrix}
+
\begin{bmatrix}
3 \\
-1
\end{bmatrix}
=
\begin{bmatrix}
4 \\
1
\end{bmatrix}.
$$

Geometrically, this places the second arrow at the tip of the first arrow.

<script type="text/tikz">
\begin{tikzpicture}
\draw[help lines, color=gray!30, dashed] (-1.9,-1.9) grid (5.9,3.9);
\draw[->,thick] (-2,0)--(6,0) node[right]{$x$};
\draw[->,thick] (0,-2)--(0,4) node[above]{$y$};
\draw[->,ultra thick, blue] (0,0)--(1,2) node[above left]{$\mathbf{v}$};
\draw[->,ultra thick, teal] (1,2)--(4,1) node[above right]{$\mathbf{w}$};
\draw[->,ultra thick, purple] (0,0)--(4,1) node[right]{$\mathbf{v}+\mathbf{w}$};
\end{tikzpicture}
</script>

## Scalar Multiplication

If we multiply a vector $\mathbf{v}$ by a scalar $s$, each component is multiplied by $s$:

$$
s\mathbf{v}  = \begin{bmatrix}
sv_1 \\
sv_2 \\
\vdots \\
sv_N
\end{bmatrix}
$$

Positive scalar multiplication changes the length without changing direction. A negative scalar reverses direction.

## Linear Combination

A linear combination is a weighted sum of vectors:

$$
c\mathbf{v} + d\mathbf{w}.
$$

Linear combinations are one of the central ideas of the course. They lead directly to span, bases, matrix multiplication, and linear systems.

## Implementation

```python
import numpy as np

v = np.array([1, 2])
w = np.array([3, -1])

print(v + w)
print(2 * v - 0.5 * w)
```

## Practice

1. Compute $[2,5]^{\mathsf T} + [4,-1]^{\mathsf T}$.
2. Compute $3[1,-2,4]^{\mathsf T}$.
3. Write $[7,1]^{\mathsf T}$ as a linear combination of $[1,0]^{\mathsf T}$ and $[0,1]^{\mathsf T}$.

## Summary

Vector addition, subtraction, scalar multiplication, and linear combinations are the basic operations used to build more advanced linear algebra.
