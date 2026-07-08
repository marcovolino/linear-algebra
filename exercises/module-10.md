---
layout: page
title: Module 10 Exercises
---

## Concept Questions

1. How do image coordinates differ from Cartesian coordinates?
2. Why is inverse mapping useful in image warping?
3. What roles do intrinsic and extrinsic camera parameters play?
4. Why is convolution linear?
5. How can point placement affect calibration conditioning?

## Calculation Questions

1. Flatten a $2\times3$ greyscale image using row-major order.
2. Compose a $90^\circ$ rotation followed by translation $(3,2)$.
3. Project $(1,2,5)$ using focal length $500$ and principal point $(320,240)$.
4. Apply a $2\times2$ averaging kernel to a small image patch.
5. Build an affine calibration design matrix from four correspondences.

## Coding Questions

1. Brighten and blend two NumPy image arrays.
2. Transform a set of homogeneous 2D points.
3. Project a set of 3D points with a camera matrix.
4. Implement a small padded image filter.
5. Fit affine parameters and report pixel RMSE.
