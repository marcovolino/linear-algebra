---
layout: lesson
title: Distance and Angles
module: 2
lesson: 4
lesson_order: 50
duration_minutes: 40
prerequisites:
  - Vectors
  - Dot product
learning_outcomes:
  - Compute the distance between two vectors.
  - Use the dot product to calculate an angle.
  - Interpret small and large angles in applied contexts.
  - Implement distance and angle calculations in NumPy.
---

## Motivation

Distances and angles let us compare vectors geometrically. In a dataset, distance can measure how different two feature vectors are. In graphics and robotics, angles tell us how directions relate to each other.

## Distance

The distance between two vectors is the length of their difference:

$$
d(\mathbf{x},\mathbf{y})
=
\lVert \mathbf{x} - \mathbf{y} \rVert_2.
$$

For two-dimensional vectors,

$$
\mathbf{x} =
\begin{bmatrix}
x_1 \\
x_2
\end{bmatrix},
\qquad
\mathbf{y} =
\begin{bmatrix}
y_1 \\
y_2
\end{bmatrix},
$$

the distance is

$$
d(\mathbf{x},\mathbf{y})
=
\sqrt{(x_1-y_1)^2 + (x_2-y_2)^2}.
$$

## Angles

From the dot product formula,

$$
\mathbf{v}\cdot\mathbf{w}
=
\lVert \mathbf{v} \rVert_2
\lVert \mathbf{w} \rVert_2
\cos\theta,
$$

we can solve for the angle:

$$
\theta
=
\cos^{-1}
\left(
\frac{\mathbf{v}\cdot\mathbf{w}}
{\lVert \mathbf{v} \rVert_2\lVert \mathbf{w} \rVert_2}
\right).
$$

This formula only works when both vectors are non-zero.

## Worked Example

Let

$$
\mathbf{v} =
\begin{bmatrix}
1 \\
0
\end{bmatrix},
\qquad
\mathbf{w} =
\begin{bmatrix}
1 \\
1
\end{bmatrix}.
$$

The dot product is

$$
\mathbf{v}\cdot\mathbf{w} = 1.
$$

The magnitudes are

$$
\lVert \mathbf{v} \rVert_2 = 1,
\qquad
\lVert \mathbf{w} \rVert_2 = \sqrt{2}.
$$

So

$$
\cos\theta
=
\frac{1}{1\sqrt{2}}
=
\frac{1}{\sqrt{2}},
$$

and therefore

$$
\theta = 45^\circ.
$$

## Implementation

```python
import numpy as np

v = np.array([1, 0])
w = np.array([1, 1])

distance = np.linalg.norm(v - w)
cos_theta = (v @ w) / (np.linalg.norm(v) * np.linalg.norm(w))
theta = np.arccos(np.clip(cos_theta, -1.0, 1.0))

print(distance)
print(np.degrees(theta))
```

The `np.clip` call protects against tiny floating-point rounding errors that can push a value just outside the valid range for `arccos`.

## Application

{% include callout.html
   type="application"
   title="Embedding similarity"
   content="Two text or image embeddings with a small angle often represent similar content, even if their raw coordinates are not identical."
%}

## Practice

1. Compute the distance between $[1,2]^{\mathsf T}$ and $[4,6]^{\mathsf T}$.
2. Find the angle between $[1,0]^{\mathsf T}$ and $[0,1]^{\mathsf T}$.
3. Explain why angle can be more useful than distance when vector length is not meaningful.

## Summary

Distance measures separation. Angle measures direction agreement. Together, they make vectors useful for comparing geometry, signals, features, and learned representations.
