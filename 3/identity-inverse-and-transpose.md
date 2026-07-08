---
layout: lesson
title: Identity, Inverse, and Transpose
module: 3
lesson: 3
lesson_order: 100
duration_minutes: 45
prerequisites:
  - Matrices
  - Matrix multiplication
learning_outcomes:
  - Identify identity, diagonal, and zero matrices.
  - Compute and interpret a matrix transpose.
  - Explain what an inverse matrix does.
  - Recognise when an inverse may not exist.
---

## Motivation

Some matrices play special roles. The identity matrix leaves vectors unchanged. The transpose swaps rows and columns. An inverse matrix, when it exists, reverses a transformation.

## Identity Matrix

The identity matrix $I$ is a square matrix with ones on the diagonal and zeros elsewhere:

$$
I_3 =
\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}.
$$

Multiplying by the identity leaves a vector unchanged:

$$
I\mathbf{x} = \mathbf{x}.
$$

For any compatible matrix $A$,

$$
AI = A,
\qquad
IA = A.
$$

## Zero and Diagonal Matrices

The zero matrix contains only zeros:

$$
0 =
\begin{bmatrix}
0 & 0 \\
0 & 0
\end{bmatrix}.
$$

A diagonal matrix has non-zero entries only on its diagonal:

$$
D =
\begin{bmatrix}
d_1 & 0 \\
0 & d_2
\end{bmatrix}.
$$

Diagonal matrices are especially useful because they scale coordinate directions independently.

## Transpose

The transpose of $A$, written $A^{\mathsf T}$, swaps rows and columns:

$$
A =
\begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6
\end{bmatrix}
\quad
\Rightarrow
\quad
A^{\mathsf T} =
\begin{bmatrix}
1 & 4 \\
2 & 5 \\
3 & 6
\end{bmatrix}.
$$

If $A$ is $m \times n$, then $A^{\mathsf T}$ is $n \times m$.

## Inverse Matrix

For a square matrix $A$, an inverse matrix $A^{-1}$ reverses the action of $A$:

$$
A^{-1}A = I,
\qquad
AA^{-1} = I.
$$

Not every square matrix has an inverse. If a matrix collapses information, such as projecting a plane onto a line, it cannot be perfectly reversed.

## Worked Example

Let

$$
A =
\begin{bmatrix}
2 & 0 \\
0 & 3
\end{bmatrix}.
$$

This matrix scales the first coordinate by $2$ and the second coordinate by $3$. Its inverse is

$$
A^{-1} =
\begin{bmatrix}
\frac{1}{2} & 0 \\
0 & \frac{1}{3}
\end{bmatrix},
$$

because

$$
A^{-1}A =
\begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix}.
$$

## Implementation

```python
import numpy as np

A = np.array([[2, 0], [0, 3]])

print(A.T)
print(np.linalg.inv(A))
print(np.linalg.inv(A) @ A)
```

For numerical work, avoid explicitly computing an inverse just to solve $A\mathbf{x}=\mathbf{b}$. Use `np.linalg.solve(A, b)` instead when possible.

## Practice

1. Write down $I_4$.
2. Compute the transpose of $\begin{bmatrix}1 & 2 \\ 3 & 4 \\ 5 & 6\end{bmatrix}$.
3. Find the inverse of $\begin{bmatrix}4 & 0 \\ 0 & 5\end{bmatrix}$.

## Summary

Identity matrices leave values unchanged, transposes swap rows and columns, and inverse matrices reverse transformations when no information has been lost.
