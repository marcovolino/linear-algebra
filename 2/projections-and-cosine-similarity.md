---
layout: lesson
title: Projections and Cosine Similarity
module: 2
lesson: 5
lesson_order: 60
duration_minutes: 45
prerequisites:
  - Dot product
  - Distance and angles
learning_outcomes:
  - Compute scalar and vector projections.
  - Explain projection as a shadow of one vector onto another.
  - Compute cosine similarity.
  - Connect projections to least squares and similarity search.
---

## Motivation

Projection answers a geometric question: how much of one vector lies in the direction of another? This idea is used in shadows, camera geometry, least-squares fitting, and feature similarity.

## Scalar Projection

If $\mathbf{u}$ is a unit vector, the scalar projection of $\mathbf{v}$ onto $\mathbf{u}$ is

$$
\mathbf{v}\cdot\mathbf{u}.
$$

This number is the signed length of the shadow of $\mathbf{v}$ in the direction $\mathbf{u}$.

If the target vector $\mathbf{w}$ is not a unit vector, first normalise it:

$$
\mathbf{u}
=
\frac{\mathbf{w}}{\lVert \mathbf{w} \rVert_2}.
$$

Then the scalar projection is

$$
\mathbf{v}\cdot
\frac{\mathbf{w}}{\lVert \mathbf{w} \rVert_2}.
$$

## Vector Projection

The vector projection of $\mathbf{v}$ onto a non-zero vector $\mathbf{w}$ is

$$
\operatorname{proj}_{\mathbf{w}}(\mathbf{v})
=
\frac{\mathbf{v}\cdot\mathbf{w}}
{\mathbf{w}\cdot\mathbf{w}}
\mathbf{w}.
$$

This gives the actual vector shadow, not just its signed length.

<script type="text/tikz">
\begin{tikzpicture}
\draw[help lines, color=gray!25, dashed] (-.2,-.2) grid (5.2,3.2);
\draw[->,thick] (0,0)--(5.5,0) node[right]{$x$};
\draw[->,thick] (0,0)--(0,3.5) node[above]{$y$};
\draw[->,ultra thick, blue] (0,0)--(4,3) node[above]{$\mathbf{v}$};
\draw[->,ultra thick, teal] (0,0)--(5,0) node[below]{$\mathbf{w}$};
\draw[->,ultra thick, purple] (0,0)--(4,0) node[below]{$\operatorname{proj}_{\mathbf{w}}(\mathbf{v})$};
\draw[dashed] (4,3)--(4,0);
\end{tikzpicture}
</script>

## Worked Example

Project

$$
\mathbf{v} =
\begin{bmatrix}
3 \\
4
\end{bmatrix}
$$

onto

$$
\mathbf{w} =
\begin{bmatrix}
1 \\
0
\end{bmatrix}.
$$

Because $\mathbf{w}$ already has length one,

$$
\operatorname{proj}_{\mathbf{w}}(\mathbf{v})
=
(\mathbf{v}\cdot\mathbf{w})\mathbf{w}.
$$

The dot product is

$$
\mathbf{v}\cdot\mathbf{w}
=
3(1) + 4(0)
=
3.
$$

So

$$
\operatorname{proj}_{\mathbf{w}}(\mathbf{v})
=
3
\begin{bmatrix}
1 \\
0
\end{bmatrix}
=
\begin{bmatrix}
3 \\
0
\end{bmatrix}.
$$

## Cosine Similarity

Cosine similarity measures the cosine of the angle between two non-zero vectors:

$$
\operatorname{cosine}(\mathbf{v},\mathbf{w})
=
\frac{\mathbf{v}\cdot\mathbf{w}}
{\lVert \mathbf{v} \rVert_2 \lVert \mathbf{w} \rVert_2}.
$$

It ranges from $-1$ to $1$:

- $1$ means the vectors point in the same direction.
- $0$ means the vectors are orthogonal.
- $-1$ means the vectors point in opposite directions.

Cosine similarity is often preferred when direction matters more than magnitude.

## Implementation

```python
import numpy as np

v = np.array([3, 4])
w = np.array([1, 0])

projection = (v @ w) / (w @ w) * w
cosine = (v @ w) / (np.linalg.norm(v) * np.linalg.norm(w))

print(projection)
print(cosine)
```

## Common Mistakes

- Forgetting that projection onto the zero vector is undefined.
- Confusing scalar projection with vector projection.
- Using cosine similarity when vector magnitude is actually meaningful.

## Practice

1. Project $[2,3]^{\mathsf T}$ onto $[1,0]^{\mathsf T}$.
2. Project $[2,3]^{\mathsf T}$ onto $[0,1]^{\mathsf T}$.
3. Compute the cosine similarity between $[1,1]^{\mathsf T}$ and $[2,0]^{\mathsf T}$.

## Summary

Projection decomposes a vector into the part that lies along another direction. Cosine similarity normalises the dot product so vectors can be compared by direction alone.
