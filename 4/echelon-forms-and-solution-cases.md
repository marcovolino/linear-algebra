---
layout: lesson
title: Echelon Forms and Solution Cases
module: 4
lesson: 3
lesson_order: 150
duration_minutes: 45
prerequisites:
  - Gaussian elimination
learning_outcomes:
  - Recognise row echelon and reduced row echelon forms.
  - Identify pivot and free variables.
  - Distinguish unique, infinite, and inconsistent systems.
  - Describe a family of solutions using a parameter.
---

## Row Echelon Form

A matrix is in row echelon form when zero rows are at the bottom, each pivot lies to the right of the pivot above it, and entries below every pivot are zero. In reduced row echelon form, each pivot is $1$ and is the only non-zero entry in its column.

## Three Solution Cases

### Unique Solution

Every variable column has a pivot:

$$
\left[
\begin{array}{cc|c}
1&0&2\\
0&1&3
\end{array}
\right].
$$

Thus $x=2$ and $y=3$.

### Infinitely Many Solutions

At least one variable is free and there is no contradiction:

$$
\left[
\begin{array}{cc|c}
1&2&5\\
0&0&0
\end{array}
\right].
$$

Let $y=t$. Then $x=5-2t$, giving

$$
\mathbf{x}
=
\begin{bmatrix}5-2t\\t\end{bmatrix}.
$$

### No Solution

A row such as

$$
\left[
\begin{array}{cc|c}
0&0&1
\end{array}
\right]
$$

claims $0=1$. The system is inconsistent.

## Application

In sensor calibration, an inconsistent system can indicate noisy or contradictory measurements. An underdetermined system has free variables, meaning the observations do not contain enough information for a unique reconstruction.

## Implementation

```python
import numpy as np

A = np.array([[1, 2], [2, 4]], dtype=float)
b = np.array([5, 10], dtype=float)

print("rank(A):", np.linalg.matrix_rank(A))
print("rank([A|b]):", np.linalg.matrix_rank(np.column_stack((A, b))))
```

Rank is developed fully in a later module. Here it is a practical diagnostic: differing ranks indicate inconsistency, while too few pivots indicate free variables.

## Practice

1. Classify the system represented by $[\,1\ \ 2\mid3;\ 0\ \ 0\mid1\,]$.
2. Describe the solutions of $x-3y=4$ using a parameter.
3. State the difference between echelon form and reduced echelon form.

## Summary

Pivots reveal a system's structure: a pivot for every variable gives a unique solution, free variables give infinitely many solutions, and a contradictory row gives no solution.
