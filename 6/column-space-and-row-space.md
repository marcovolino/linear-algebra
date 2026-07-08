---
layout: lesson
title: Column Space and Row Space
module: 6
lesson: 1
lesson_order: 230
duration_minutes: 45
prerequisites:
  - Span, basis, and dimension
  - Echelon forms
learning_outcomes:
  - Define column space and row space.
  - Find bases using pivot positions.
  - Interpret the column space as possible outputs.
  - Relate row operations to the row space.
---

## Column Space

For an $m\times n$ matrix $A$, the column space is

$$
\operatorname{Col}(A)=\operatorname{span}\{\mathbf{a}_1,\ldots,\mathbf{a}_n\}.
$$

It is a subspace of $\mathbb{R}^m$. Since $A\mathbf{x}$ is a linear combination of the columns, $\operatorname{Col}(A)$ contains every possible output of the transformation.

The system $A\mathbf{x}=\mathbf{b}$ is consistent exactly when $\mathbf{b}\in\operatorname{Col}(A)$.

## Row Space

The row space is the span of the rows of $A$, viewed as vectors in $\mathbb{R}^n$. Elementary row operations preserve the row space, so the non-zero rows of an echelon form give a convenient basis.

## Worked Example

Let

$$
A=\begin{bmatrix}
1&2&3\\
2&4&6\\
0&1&1
\end{bmatrix}.
$$

Row reduction gives

$$
\begin{bmatrix}
1&0&1\\
0&1&1\\
0&0&0
\end{bmatrix}.
$$

The pivots are in columns $1$ and $2$. A basis for the column space uses the corresponding columns of the original matrix:

$$
\left\{
\begin{bmatrix}1\\2\\0\end{bmatrix},
\begin{bmatrix}2\\4\\1\end{bmatrix}
\right\}.
$$

A basis for the row space is given by the two non-zero reduced rows.

{% include callout.html
   type="warning"
   title="Use original columns"
   content="Pivot positions come from the echelon form, but a basis for the column space must use those columns from the original matrix."
%}

## Implementation

```python
import numpy as np

A = np.array([[1, 2, 3], [2, 4, 6], [0, 1, 1]], dtype=float)
print(np.linalg.matrix_rank(A))
```

## Practice

1. Find a basis for the column space of $\begin{bmatrix}1&2\\2&4\end{bmatrix}$.
2. State the ambient space of the row space of a $4\times7$ matrix.
3. Explain why consistency means $\mathbf{b}$ belongs to the column space.

## Summary

The column space describes reachable outputs; the row space describes independent constraints on inputs. Pivot positions reveal bases for both.
