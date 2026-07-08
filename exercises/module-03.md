---
layout: page
title: Module 3 Exercises
---

These exercises support the matrices and linear transformations module.

## Concept Questions

1. Why must the inner dimensions match for matrix multiplication?
2. Explain why matrix multiplication is usually not commutative.
3. What does the identity matrix do to a vector?
4. What geometric action does an inverse matrix perform?
5. Why do the columns of a matrix describe where basis vectors go?

## Calculation Questions

1. State the dimensions of the product of a $3 \times 4$ matrix and a $4 \times 2$ matrix.
2. Compute
   $$
   \begin{bmatrix}
   1 & 2 \\
   3 & 4
   \end{bmatrix}
   \begin{bmatrix}
   0 & 1 \\
   2 & 3
   \end{bmatrix}.
   $$
3. Compute the transpose of
   $$
   \begin{bmatrix}
   1 & 0 & 2 \\
   -1 & 3 & 4
   \end{bmatrix}.
   $$
4. Find the inverse of
   $$
   \begin{bmatrix}
   2 & 0 \\
   0 & 5
   \end{bmatrix}.
   $$
5. Apply
   $$
   \begin{bmatrix}
   0 & -1 \\
   1 & 0
   \end{bmatrix}
   $$
   to $[1,0]^{\mathsf T}$ and $[0,1]^{\mathsf T}$.

## Coding Questions

1. Use NumPy to multiply two compatible matrices.
2. Use NumPy to transform a list of 2D points by a scaling matrix.
3. Use NumPy to verify that $A^{-1}A$ is approximately the identity for an invertible matrix.
