---
layout: lesson
title: Matrix Multiplication
module: 3
lesson: 2
lesson_order: 90
duration_minutes: 45
prerequisites:
  - Matrices
  - Dot product
learning_outcomes:
  - Check when two matrices can be multiplied.
  - Compute matrix products using row-column dot products.
  - Interpret matrix multiplication as composition.
  - Implement matrix multiplication with NumPy.
---

## Motivation

Matrix multiplication is how we apply several linear operations in sequence. In graphics, one matrix may rotate an object and another may scale it. Multiplying the matrices gives a single matrix that performs both operations.

## Compatibility

If $A$ is an $m \times n$ matrix and $B$ is an $n \times p$ matrix, then the product $AB$ is defined and has size $m \times p$.

The inner dimensions must match:

$$
(m \times n)(n \times p) = m \times p.
$$

For example, a $2 \times 3$ matrix can multiply a $3 \times 4$ matrix, producing a $2 \times 4$ matrix.

## Row-Column Rule

Each entry of $AB$ is a dot product between a row of $A$ and a column of $B$:

$$
(AB)_{ij}
=
\sum_{k=1}^{n} a_{ik}b_{kj}.
$$

For

$$
A =
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix},
\qquad
B =
\begin{bmatrix}
e & f \\
g & h
\end{bmatrix},
$$

the product is

$$
AB =
\begin{bmatrix}
ae + bg & af + bh \\
ce + dg & cf + dh
\end{bmatrix}.
$$

## Worked Example

Let

$$
A =
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix},
\qquad
B =
\begin{bmatrix}
2 & 0 \\
1 & 5
\end{bmatrix}.
$$

Then

$$
AB =
\begin{bmatrix}
1(2) + 2(1) & 1(0) + 2(5) \\
3(2) + 4(1) & 3(0) + 4(5)
\end{bmatrix}
=
\begin{bmatrix}
4 & 10 \\
10 & 20
\end{bmatrix}.
$$

## Order Matters

Matrix multiplication is usually not commutative:

$$
AB \neq BA.
$$

The order describes the order of operations. If a vector is transformed by $B$ and then by $A$, the combined operation is $AB\mathbf{x}$.

## Implementation

```python
import numpy as np

A = np.array([[1, 2], [3, 4]])
B = np.array([[2, 0], [1, 5]])

print(A @ B)
```

Use `@` or `np.matmul` for matrix multiplication. The expression `A * B` performs entry-wise multiplication in NumPy.

## Practice

1. State the size of the product of a $4 \times 2$ matrix and a $2 \times 5$ matrix.
2. Compute $\begin{bmatrix}1 & 0 \\ 2 & 1\end{bmatrix}\begin{bmatrix}3 & 4 \\ 5 & 6\end{bmatrix}$.
3. Give an example of two matrices $A$ and $B$ where $AB \neq BA$.

## Summary

Matrix multiplication uses row-column dot products. It encodes composition, so the order matters and the dimensions must match.
