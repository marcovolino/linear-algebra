---
layout: lesson
title: Vectors
module: 2
lesson: 1
lesson_order: 20
duration_minutes: 35
prerequisites:
  - Scalars
  - Coordinate axes
learning_outcomes:
  - Represent vectors using component notation.
  - Compute vector magnitude using the Euclidean norm.
  - Interpret vectors geometrically as arrows or displacements.
  - Convert a non-zero vector into a unit vector.
---

## Motivation

A vector is a mathematical object with components that can encode magnitude and direction. Vectors can represent physical quantities such as force and velocity, but they also represent pixels, features, signals, word embeddings, and points in 2D or 3D graphics.

{% include callout.html
   type="application"
   title="AI connection"
   content="In machine learning, each row of a data matrix is often treated as a feature vector. Similar vectors often correspond to similar examples."
%}

## Definitions and Notation

A vector is commonly written as a bold lowercase letter, such as $\mathbf{v}$. The scalar components of an $N$-dimensional vector are written using subscripts:

$$
\mathbf{v} = \begin{bmatrix}
v_1 \\
v_2 \\
\vdots \\
v_N
\end{bmatrix}
$$

Here, $v_1$ is the first component, $v_2$ is the second component, and so on.

## Magnitude

The magnitude, or Euclidean norm, of a vector is denoted $\lVert \mathbf{v} \rVert_2$. For a vector with $N$ components,

$$
\lVert \mathbf{v} \rVert_2 =
\sqrt{v_1^2 + v_2^2 + \dots + v_N^2}
$$

or, more compactly,

$$
\lVert \mathbf{v} \rVert_2 =
\sqrt{\sum_{n=1}^{N} v_n^2}.
$$

For $\mathbf{v} = [4,3]^{\mathsf T}$, the magnitude is

$$
\lVert \mathbf{v} \rVert_2 = \sqrt{4^2 + 3^2} = 5.
$$

## Geometric Interpretation

In two dimensions, a vector can be drawn as an arrow from the origin to a point. The components describe how far the arrow moves in each coordinate direction.

<script type="text/tikz">
\begin{tikzpicture}
\draw[help lines, color=gray!30, dashed] (-4.9,-4.9) grid (4.9,4.9);
\draw[->,ultra thick] (-5,0)--(5,0) node[right]{$x$};
\draw[->,ultra thick] (0,-5)--(0,5) node[above]{$y$};
\draw[->,ultra thick, blue] (0,0)--(4,3) node[right]{$\mathbf{v}$};
\draw[dashed] (4,0)--(4,3);
\draw[dashed] (0,3)--(4,3);
\node[below] at (4,0) {$4$};
\node[left] at (0,3) {$3$};
\end{tikzpicture}
</script>

## Unit Vectors

A unit vector has magnitude one. It keeps the direction of a vector but removes its scale. For a non-zero vector $\mathbf{v}$, the corresponding unit vector is

$$
\mathbf{u} = \frac{\mathbf{v}}{\lVert \mathbf{v} \rVert_2}.
$$

For $\mathbf{v} = [4,3]^{\mathsf T}$,

$$
\mathbf{u}
= \frac{1}{5}
\begin{bmatrix}
4 \\
3
\end{bmatrix}
=
\begin{bmatrix}
0.8 \\
0.6
\end{bmatrix}.
$$

## Implementation

```python
import numpy as np

v = np.array([4, 3])
magnitude = np.linalg.norm(v)
unit = v / magnitude
print(magnitude, unit)
```

## Common Mistakes

- Confusing the vector $\mathbf{v}$ with one of its components $v_i$.
- Using $\lvert \mathbf{v} \rvert$ ambiguously when $\lVert \mathbf{v} \rVert_2$ is clearer.
- Trying to normalise the zero vector. The zero vector has no direction, so it has no unit vector.

## Practice

1. Compute the magnitude of $\mathbf{v} = [6,8]^{\mathsf T}$.
2. Find the unit vector in the direction of $\mathbf{v} = [1,2,2]^{\mathsf T}$.
3. Give one physical and one AI example of a vector.

## Summary

Vectors are ordered lists of numbers with algebraic and geometric interpretations. Their magnitude measures length, and unit vectors describe direction without scale.
