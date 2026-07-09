---
layout: lesson
title: Repeated Transformations and Stability
module: 8
lesson: 4
lesson_order: 360
duration_minutes: 45
prerequisites:
  - Diagonalisation
learning_outcomes:
  - Analyse repeated matrix transformations.
  - Relate eigenvalue magnitude to growth and decay.
  - Define spectral radius.
  - Identify dominant long-term modes.
---

## Discrete Dynamics

A linear dynamical system evolves by

$$
\mathbf{x}_{k+1}=A\mathbf{x}_k,
\qquad
\mathbf{x}_k=A^k\mathbf{x}_0.
$$

If $\mathbf{x}_0$ is expanded in an eigenvector basis,

$$
\mathbf{x}_0=\sum_i c_i\mathbf{v}_i,
$$

then

$$
\mathbf{x}_k=\sum_i c_i\lambda_i^k\mathbf{v}_i.
$$

## Eigenvalue Magnitude

- $\lvert\lambda\rvert<1$: the mode decays.
- $\lvert\lambda\rvert>1$: the mode grows.
- $\lambda<0$: its sign alternates.
- $\lvert\lambda\rvert=1$: it persists without magnitude decay.

The spectral radius is

$$
\rho(A)=\max_i|\lambda_i|.
$$

For a diagonalizable discrete system, $\rho(A)<1$ implies every state tends to zero.

## Dominant Direction

When one eigenvalue has strictly largest magnitude, repeated multiplication often aligns a generic starting vector with its eigenvector. This idea underlies the power method and several graph-ranking algorithms.

## Implementation

```python
import numpy as np

A = np.array([[0.9, 0.0], [0.0, 0.5]])
x = np.array([1.0, 2.0])

for _ in range(10):
    x = A @ x
print(x)
print(max(abs(np.linalg.eigvals(A))))
```

## Practice

1. Predict the behaviour of modes with eigenvalues $0.8$, $-1.1$, and $1$.
2. Find the spectral radius of $\operatorname{diag}(0.2,-0.7,1.3)$.
3. Explain why the dominant eigenvector emerges under repeated multiplication.

## Summary

Eigenvalues turn repeated matrix application into scalar growth and decay, revealing dominant modes and system stability.
