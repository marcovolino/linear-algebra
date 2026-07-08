---
layout: lesson
title: Least-Squares Fitting
module: 7
lesson: 3
lesson_order: 300
duration_minutes: 50
prerequisites:
  - Column space and projections
  - Overdetermined systems
learning_outcomes:
  - Formulate a least-squares problem.
  - Derive and use the normal equations.
  - Fit a line to data.
  - Interpret residual orthogonality.
---

## Closest Attainable Output

When $A\mathbf{x}=\mathbf{b}$ is inconsistent, least squares chooses

$$
\widehat{\mathbf{x}}
=\arg\min_{\mathbf{x}}\lVert A\mathbf{x}-\mathbf{b}\rVert_2^2.
$$

The fitted vector $A\widehat{\mathbf{x}}$ is the projection of $\mathbf{b}$ onto $\operatorname{Col}(A)$. Therefore the residual

$$
\mathbf{r}=\mathbf{b}-A\widehat{\mathbf{x}}
$$

is orthogonal to every column of $A$, giving the normal equations

$$
A^{\mathsf T}A\widehat{\mathbf{x}}=A^{\mathsf T}\mathbf{b}.
$$

## Line Fitting

To fit $y=c+mx$ through points $(x_i,y_i)$, use one row $[1,x_i]$ per observation:

$$
A=\begin{bmatrix}
1&x_1\\
\vdots&\vdots\\
1&x_m
\end{bmatrix},
\qquad
\mathbf{x}=\begin{bmatrix}c\\m\end{bmatrix}.
$$

## Implementation

```python
import numpy as np

x_data = np.array([0, 1, 2, 3], dtype=float)
y_data = np.array([1.0, 2.2, 2.9, 4.1])
A = np.column_stack((np.ones_like(x_data), x_data))

parameters, _, _, _ = np.linalg.lstsq(A, y_data, rcond=None)
residual = y_data - A @ parameters
print("intercept, slope:", parameters)
print("orthogonality:", A.T @ residual)
```

{% include callout.html
   type="warning"
   title="Normal equations in practice"
   content="The normal equations explain the geometry, but QR or SVD-based solvers are usually more numerically stable than explicitly forming A transpose A."
%}

## Applications

Least squares supports line fitting, sensor calibration, and approximating signals using a limited collection of basis functions.

## Practice

1. Build the design matrix for fitting a line to three points.
2. Explain why $A^{\mathsf T}\mathbf{r}=\mathbf{0}$.
3. Fit a line to $(0,1)$, $(1,2)$, and $(2,2)$ with NumPy.

## Summary

Least squares projects observations onto the column space of a model matrix, producing the smallest residual when no exact fit exists.
