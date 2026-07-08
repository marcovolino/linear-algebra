---
layout: lesson
title: Matrices and Matrix Operations
module: 3
lesson: 1
lesson_order: 80
duration_minutes: 45
prerequisites:
  - Vectors
  - Vector operations
learning_outcomes:
  - Read matrix dimensions and entries.
  - Add matrices and multiply them by scalars.
  - Compute a simple matrix-vector product.
  - Explain why matrices can represent transformations.
---

## Motivation

Matrices organise many numbers at once. They can store datasets, images, systems of equations, and transformations. A greyscale image is a matrix of pixel values; a neural-network layer applies a matrix to a feature vector; a 2D graphics transform uses a matrix to move points.

## Matrix Notation

An $m \times n$ matrix has $m$ rows and $n$ columns:

$$
A =
\begin{bmatrix}
a_{11}  & a_{12}    & \cdots & a_{1n} \\
a_{21}  & a_{22}    & \cdots & a_{2n} \\
\vdots  & \vdots    & \ddots & \vdots \\
a_{m1}  & a_{m2}    & \cdots & a_{mn}
\end{bmatrix}.
$$

The entry $a_{ij}$ is in row $i$, column $j$.

## Addition and Scalar Multiplication

Matrices of the same size are added component by component:

$$
A + B =
\begin{bmatrix}
a_{11}+b_{11} & a_{12}+b_{12} \\
a_{21}+b_{21} & a_{22}+b_{22}
\end{bmatrix}.
$$

Scalar multiplication also acts component by component:

$$
cA =
\begin{bmatrix}
ca_{11} & ca_{12} \\
ca_{21} & ca_{22}
\end{bmatrix}.
$$

## Matrix-Vector Products

A matrix can multiply a vector when the number of matrix columns equals the number of vector components.

$$
\begin{bmatrix}
2 & 0 \\
0 & 3
\end{bmatrix}
\begin{bmatrix}
x \\
y
\end{bmatrix}
=
\begin{bmatrix}
2x \\
3y
\end{bmatrix}.
$$

This matrix scales the $x$-coordinate by 2 and the $y$-coordinate by 3.

<script type="text/tikz">
\begin{tikzpicture}
\draw[help lines, color=gray!30, dashed] (-.2,-.2) grid (4.2,4.2);
\draw[->,thick] (0,0)--(4.5,0) node[right]{$x$};
\draw[->,thick] (0,0)--(0,4.5) node[above]{$y$};
\draw[->,ultra thick, blue] (0,0)--(1,1) node[above left]{$\mathbf{v}$};
\draw[->,ultra thick, purple] (0,0)--(2,3) node[right]{$A\mathbf{v}$};
\end{tikzpicture}
</script>

## Worked Example

Let

$$
A =
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix},
\qquad
\mathbf{x} =
\begin{bmatrix}
5 \\
6
\end{bmatrix}.
$$

Then

$$
A\mathbf{x}
=
\begin{bmatrix}
1(5) + 2(6) \\
3(5) + 4(6)
\end{bmatrix}
=
\begin{bmatrix}
17 \\
39
\end{bmatrix}.
$$

## Implementation

```python
import numpy as np

A = np.array([[1, 2], [3, 4]])
x = np.array([5, 6])

print(A @ x)
```

## Common Mistakes

- Adding matrices with different dimensions.
- Forgetting that matrix multiplication is not usually commutative: $AB \neq BA$.
- Confusing entry-wise multiplication with matrix multiplication.

## Practice

1. What are the dimensions of a dataset matrix with 40 examples and 6 features?
2. Compute $2A$ for $A = \begin{bmatrix} 1 & -1 \\ 0 & 3 \end{bmatrix}$.
3. Compute $A\mathbf{x}$ for $A = \begin{bmatrix} 2 & 1 \\ 1 & 0 \end{bmatrix}$ and $\mathbf{x} = [3,4]^{\mathsf T}$.

## Summary

Matrices extend vector ideas to rectangular arrays. They store data and represent operations on vectors, which is why they are central to systems, graphics, vision, and machine learning.
