---
layout: lesson
title: Pseudoinverse
module: 9
lesson: 4
lesson_order: 420
duration_minutes: 45
prerequisites:
  - Singular value decomposition
  - Least squares
learning_outcomes:
  - Construct the Moore-Penrose pseudoinverse.
  - Solve least-squares systems.
  - Identify minimum-norm solutions.
  - Explain the effect of small singular values.
---

## Generalised Inversion

If

$$
A=U\Sigma V^{\mathsf T},
$$

the pseudoinverse is

$$
A^+=V\Sigma^+U^{\mathsf T},
$$

where each non-zero singular value is replaced by its reciprocal.

The vector

$$
\widehat{\mathbf{x}}=A^+\mathbf{b}
$$

is a least-squares solution. If several exact solutions exist, it is the one with minimum Euclidean norm.

## Worked Example

For

$$
A=\begin{bmatrix}1&0&0\\0&1&0\end{bmatrix},
\qquad
\mathbf{b}=\begin{bmatrix}3\\4\end{bmatrix},
$$

all exact solutions are $[3,4,t]^{\mathsf T}$. The pseudoinverse chooses $t=0$, producing the shortest solution.

## Implementation

```python
import numpy as np

A = np.array([[1, 0, 0], [0, 1, 0]], dtype=float)
b = np.array([3, 4], dtype=float)

x = np.linalg.pinv(A) @ b
print(x)
print(A @ x)
```

{% include callout.html
   type="warning"
   title="Small singular values"
   content="Reciprocating a tiny singular value greatly amplifies noise. Practical pseudoinverses use a tolerance and treat sufficiently small values as zero."
%}

## Practice

1. Find the pseudoinverse of $\operatorname{diag}(4,0)$.
2. Explain minimum-norm solution in geometric terms.
3. Compare `pinv(A) @ b` with `lstsq(A, b)` in NumPy.

## Summary

The pseudoinverse uses SVD to extend inversion to rectangular and singular matrices while selecting useful least-squares and minimum-norm solutions.
