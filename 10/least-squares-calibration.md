---
layout: lesson
title: Least-Squares Calibration
module: 10
lesson: 5
lesson_order: 490
duration_minutes: 50
prerequisites:
  - Camera projection
  - Least squares and SVD
learning_outcomes:
  - Form a calibration system from correspondences.
  - Estimate linear model parameters by least squares.
  - Interpret reprojection residuals.
  - Recognise degeneracy and conditioning concerns.
---

## Calibration from Measurements

Calibration estimates model parameters from known inputs and observed image outputs. Repeated measurements create a system

$$
A\boldsymbol{\theta}\approx\mathbf{b},
$$

where $\boldsymbol{\theta}$ contains unknown parameters. More correspondences than parameters usually produce an overdetermined system.

## Simple Affine Calibration

Suppose one image coordinate follows

$$
u=aX+bY+t.
$$

Each correspondence contributes a row $[X,Y,1]$ to $A$ and its measured $u$ to $\mathbf{b}$.

## Implementation

```python
import numpy as np

world = np.array([[0, 0], [1, 0], [0, 1], [1, 1]], dtype=float)
observed_u = np.array([2.0, 5.1, 0.9, 4.0])
A = np.column_stack((world, np.ones(len(world))))

theta, _, rank, singular_values = np.linalg.lstsq(A, observed_u, rcond=None)
residuals = observed_u - A @ theta
print("a, b, t:", theta)
print("rank:", rank)
print("RMSE:", np.sqrt(np.mean(residuals**2)))
```

## Validation

Residuals should be reported in meaningful units such as pixels. Hold-out points test whether the model generalises beyond its calibration data.

Poorly distributed or repeated points can make $A$ rank deficient or ill-conditioned. SVD reveals weakly constrained parameter combinations.

## Application

The same pattern supports camera calibration, geometric registration, feature transformation, and linear reconstruction models.

## Practice

1. Build $A$ for three affine correspondences.
2. Explain why collinear calibration points can be problematic.
3. Compare training residuals with hold-out reprojection errors.

## Summary

Calibration converts geometric measurements into a least-squares system. Rank, singular values, and residuals reveal whether the estimate is identifiable and reliable.
