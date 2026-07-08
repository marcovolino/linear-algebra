---
layout: lesson
title: Low-Rank Approximation
module: 9
lesson: 3
lesson_order: 410
duration_minutes: 50
prerequisites:
  - SVD geometry
  - Rank
learning_outcomes:
  - Construct a truncated SVD.
  - Explain optimal low-rank approximation.
  - Estimate storage savings.
  - Apply SVD to image compression and noise reduction.
---

## Truncated SVD

The SVD can be written as a sum of rank-one matrices:

$$
A=\sum_{i=1}^{r}\sigma_i\mathbf{u}_i\mathbf{v}_i^{\mathsf T}.
$$

Keeping only the first $k$ terms gives

$$
A_k=\sum_{i=1}^{k}\sigma_i\mathbf{u}_i\mathbf{v}_i^{\mathsf T}.
$$

The Eckart-Young theorem says $A_k$ is the best rank-$k$ approximation under the spectral and Frobenius norms.

## Image Compression

A greyscale $m\times n$ image stores $mn$ values. A rank-$k$ approximation stores approximately

$$
k(m+n+1)
$$

values: $k$ singular values and $k$ columns from each singular-vector matrix.

## Implementation

```python
import numpy as np

image = np.array([
    [0, 20, 30, 20],
    [10, 40, 50, 30],
    [20, 50, 60, 40],
], dtype=float)

U, s, Vt = np.linalg.svd(image, full_matrices=False)
k = 2
compressed = U[:, :k] @ np.diag(s[:k]) @ Vt[:k, :]
relative_error = np.linalg.norm(image - compressed) / np.linalg.norm(image)
print(relative_error)
```

## Choosing Rank

The retained energy fraction is often measured by

$$
\frac{\sum_{i=1}^{k}\sigma_i^2}{\sum_i\sigma_i^2}.
$$

Rank is a tradeoff between compactness and reconstruction quality.

## Practice

1. Write the rank-one expansion of a two-term SVD.
2. Compare storage for a $1000\times800$ image using rank $20$.
3. Explain why truncation can reduce noise.

## Summary

Truncated SVD preserves the strongest matrix structure using fewer parameters, enabling compression, denoising, and dimensionality reduction.
