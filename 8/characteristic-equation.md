---
layout: lesson
title: Characteristic Equation
module: 8
lesson: 2
lesson_order: 340
duration_minutes: 50
prerequisites:
  - Eigenvalues and eigenvectors
  - Determinants of small matrices
learning_outcomes:
  - Derive the characteristic equation.
  - Find eigenvalues of a 2 by 2 matrix.
  - Compute eigenspaces.
  - Distinguish algebraic and geometric multiplicity.
---

## Finding Eigenvalues

A non-zero solution to

$$
(A-\lambda I)\mathbf{v}=\mathbf{0}
$$

exists exactly when $A-\lambda I$ is singular. Therefore eigenvalues satisfy

$$
\det(A-\lambda I)=0.
$$

This is the characteristic equation.

## Worked Example

Let

$$
A=\begin{bmatrix}4&1\\2&3\end{bmatrix}.
$$

Then

$$
\det(A-\lambda I)
=(4-\lambda)(3-\lambda)-2
=\lambda^2-7\lambda+10.
$$

Factoring gives $(\lambda-5)(\lambda-2)=0$, so the eigenvalues are $5$ and $2$.

For $\lambda=5$, solving $(A-5I)\mathbf{v}=0$ gives an eigenspace spanned by $[1,1]^{\mathsf T}$. For $\lambda=2$, it is spanned by $[1,-2]^{\mathsf T}$.

## Multiplicity

Algebraic multiplicity counts how often an eigenvalue occurs as a root of the characteristic polynomial. Geometric multiplicity is the dimension of its eigenspace. The geometric multiplicity is at least one and no greater than the algebraic multiplicity.

## Implementation

```python
import numpy as np

A = np.array([[4, 1], [2, 3]], dtype=float)
values, vectors = np.linalg.eig(A)
print(values)
print(vectors)
```

Numerical output may order eigenvalues differently and scale eigenvectors differently; both are mathematically harmless.

## Practice

1. Find the characteristic polynomial of $\begin{bmatrix}2&1\\0&3\end{bmatrix}$.
2. Find a basis for each eigenspace.
3. Verify each eigenpair by multiplication.

## Summary

The characteristic equation finds scalings that make $A-\lambda I$ singular; its null space then supplies the corresponding eigenvectors.
