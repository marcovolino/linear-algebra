---
layout: lesson
title: Convolution as a Linear Operation
module: 10
lesson: 4
lesson_order: 480
duration_minutes: 45
prerequisites:
  - Images as matrices
  - Linear transformations
learning_outcomes:
  - Apply a small convolution kernel.
  - Explain convolution's linearity.
  - Recognise boundary and padding choices.
  - Connect kernels with filtering and feature detection.
---

## Local Linear Filtering

For image $I$ and kernel $K$, a 2D discrete convolution combines nearby pixels:

$$
Y[i,j]=\sum_m\sum_n K[m,n]I[i-m,j-n].
$$

Many software libraries implement cross-correlation, which omits the kernel flip. The distinction matters when kernels are not symmetric.

## Linearity

For images $I_1,I_2$ and scalars $a,b$,

$$
K*(aI_1+bI_2)=a(K*I_1)+b(K*I_2).
$$

After flattening an image, a fixed convolution can therefore be represented by a large sparse matrix.

## Common Kernels

A blur averages neighbouring pixels, while derivative-like kernels highlight intensity changes and edges. Padding determines how the operation handles image boundaries.

## Implementation

```python
import numpy as np

image = np.array([[0, 0, 0], [0, 1, 1], [0, 1, 1]], dtype=float)
kernel = np.array([[1, 0, -1], [1, 0, -1], [1, 0, -1]], dtype=float)

padded = np.pad(image, 1)
output = np.zeros_like(image)
for i in range(image.shape[0]):
    for j in range(image.shape[1]):
        patch = padded[i:i + 3, j:j + 3]
        output[i, j] = np.sum(patch * kernel)
print(output)
```

## Practice

1. Verify convolution linearity with two small arrays.
2. Describe the effect of a $3\times3$ averaging kernel.
3. Compare zero, reflection, and valid padding.

## Summary

Convolution is a structured linear transformation that reuses a local kernel across an image, enabling efficient smoothing and feature extraction.
