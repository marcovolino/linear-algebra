---
layout: lesson
title: Images as Matrices
module: 10
lesson: 1
lesson_order: 450
duration_minutes: 45
prerequisites:
  - Matrices and NumPy
learning_outcomes:
  - Represent greyscale and colour images as arrays.
  - Distinguish image coordinates from Cartesian coordinates.
  - Apply matrix operations to pixel data.
  - Interpret images as vectors for linear models.
---

## Image Arrays

A greyscale image with height $H$ and width $W$ is an $H\times W$ matrix. A colour image is commonly an $H\times W\times3$ array containing red, green, and blue channels.

Pixel indexing usually starts at the top-left:

$$
I[v,u],
$$

where $u$ increases rightward and $v$ increases downward. This differs from a Cartesian $xy$-plane.

## Linear Image Operations

Brightness scaling is scalar multiplication, blending aligned images is a linear combination, and flattening creates a feature vector:

$$
\mathbf{x}=\operatorname{vec}(I)\in\mathbb{R}^{HW}.
$$

An image dataset can then be stored with one flattened image per row.

## Implementation

```python
import numpy as np

image = np.array([
    [20, 60, 100],
    [40, 80, 120],
], dtype=float)

brighter = np.clip(1.4 * image, 0, 255)
features = image.reshape(-1)
print(image.shape, features.shape)
```

## Application

Once images are arrays, matrix decompositions can expose latent structure, transformations can warp coordinates, and linear filters can detect local patterns.

## Practice

1. State the shape of a $480\times640$ RGB image.
2. How many entries are in its flattened vector?
3. Write a linear blend of two aligned images.

## Summary

Images are structured numerical arrays. Treating their pixels or features as vectors opens the full linear-algebra toolkit while coordinate conventions preserve spatial meaning.
