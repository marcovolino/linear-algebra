---
layout: lesson
title: Linear Independence
module: 5
lesson: 3
lesson_order: 200
duration_minutes: 45
prerequisites:
  - Linear combinations and span
  - Gaussian elimination
learning_outcomes:
  - Define linear independence and dependence.
  - Test independence by solving a homogeneous system.
  - Identify redundant spanning vectors.
  - Connect pivots with independence.
---

## Independence

Vectors $\mathbf{v}_1,\ldots,\mathbf{v}_k$ are linearly independent if

$$
c_1\mathbf{v}_1+\cdots+c_k\mathbf{v}_k=\mathbf{0}
$$

has only the solution $c_1=\cdots=c_k=0$. A non-zero solution shows dependence: at least one vector can be built from the others.

## Matrix Test

Place the vectors in the columns of $A$. The columns are independent exactly when

$$
A\mathbf{c}=\mathbf{0}
$$

has no free variables. Equivalently, every column is a pivot column.

## Worked Example

The vectors

$$
\mathbf{v}_1=\begin{bmatrix}1\\2\end{bmatrix},
\quad
\mathbf{v}_2=\begin{bmatrix}2\\4\end{bmatrix}
$$

are dependent because $2\mathbf{v}_1-\mathbf{v}_2=\mathbf{0}$. The second vector adds no new direction to the span.

In contrast, $[1,2]^{\mathsf T}$ and $[0,1]^{\mathsf T}$ are independent because neither is a scalar multiple of the other.

{% include callout.html
   type="application"
   title="Redundant features"
   content="If one feature is an exact linear combination of others, it contributes no new linear information. Independence helps identify a compact feature representation."
%}

## Implementation

```python
import numpy as np

A = np.array([[1, 2], [2, 4]], dtype=float)
independent = np.linalg.matrix_rank(A) == A.shape[1]
print(independent)
```

## Practice

1. Test whether $[1,0,1]^{\mathsf T}$, $[0,1,1]^{\mathsf T}$, and $[1,1,2]^{\mathsf T}$ are independent.
2. Explain why a set containing the zero vector is dependent.
3. Can four vectors in $\mathbb{R}^3$ be independent?

## Summary

Independent vectors contribute distinct directions. Dependence reveals redundancy and appears as free variables in the associated homogeneous system.
