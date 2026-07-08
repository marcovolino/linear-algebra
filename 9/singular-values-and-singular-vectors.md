---
layout: lesson
title: Singular Values and Singular Vectors
module: 9
lesson: 1
lesson_order: 390
duration_minutes: 50
prerequisites:
  - Eigenvalues and eigenvectors
  - Orthonormal bases
learning_outcomes:
  - State the singular value decomposition.
  - Identify left and right singular vectors.
  - Relate singular values to eigenvalues.
  - Compute an SVD with NumPy.
---

## The Factorisation

Every real $m\times n$ matrix has a singular value decomposition

$$
A=U\Sigma V^{\mathsf T},
$$

where $U$ and $V$ have orthonormal columns and $\Sigma$ contains non-negative singular values

$$
\sigma_1\geq\sigma_2\geq\cdots\geq0.
$$

The columns $\mathbf{v}_i$ of $V$ are right singular vectors, and the columns $\mathbf{u}_i$ of $U$ are left singular vectors:

$$
A\mathbf{v}_i=\sigma_i\mathbf{u}_i.
$$

## Connection to Eigenvalues

The right singular vectors are eigenvectors of $A^{\mathsf T}A$:

$$
A^{\mathsf T}A\mathbf{v}_i=\sigma_i^2\mathbf{v}_i.
$$

Unlike eigenvalue decomposition, SVD applies to rectangular matrices and always supplies orthonormal directions.

## Worked Example

For $A=\operatorname{diag}(3,1)$, the standard basis vectors are both left and right singular vectors, and the singular values are $3$ and $1$.

## Implementation

```python
import numpy as np

A = np.array([[3, 0], [0, 1]], dtype=float)
U, singular_values, Vt = np.linalg.svd(A, full_matrices=False)
Sigma = np.diag(singular_values)

print(singular_values)
print(np.allclose(A, U @ Sigma @ Vt))
```

## Practice

1. Find the singular values of $\operatorname{diag}(4,2)$.
2. Verify $A\mathbf{v}_i=\sigma_i\mathbf{u}_i$ numerically.
3. Explain one advantage of SVD over eigenvalue decomposition.

## Summary

SVD describes any matrix using orthonormal input directions, non-negative scale factors, and orthonormal output directions.
