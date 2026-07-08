---
layout: page
title: Module 6 Exercises
---

These exercises support the rank and matrix subspaces module.

## Concept Questions

1. Why is the column space the set of possible outputs?
2. What does the null space reveal about a transformation?
3. How do rank and nullity divide the input directions?
4. How can many measurements still be redundant?

## Calculation Questions

1. Find bases for the column and row spaces of $\begin{bmatrix}1&2\\2&4\end{bmatrix}$.
2. Find a basis for the null space of $\begin{bmatrix}1&2&-1\end{bmatrix}$.
3. Find the rank and nullity of a $5\times8$ matrix with four pivots.
4. Determine whether a $3\times5$ matrix can have full column rank.
5. Describe all solutions of $A\mathbf{x}=\mathbf{b}$ if one solution is known and the null space has basis $\{\mathbf{z}_1,\mathbf{z}_2\}$.

## Coding Questions

1. Compute matrix rank using `np.linalg.matrix_rank`.
2. Extract a numerical null-space basis using singular value decomposition.
3. Compare least-squares and pseudoinverse solutions.
4. Verify that adding a null vector does not change $A\mathbf{x}$.

## Application Questions

1. Interpret nullity in an image reconstruction problem.
2. Explain how low rank supports data compression.
3. Distinguish redundant sensors from sensors that add an independent measurement.
