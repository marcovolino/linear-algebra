---
layout: page
title: Module 7 Exercises
---

## Concept Questions

1. Why are non-zero orthogonal vectors independent?
2. Why do orthogonal matrices preserve lengths?
3. What geometric condition defines a least-squares residual?
4. Why is QR preferable to explicitly forming normal equations?

## Calculation Questions

1. Normalise $[3,4]^{\mathsf T}$.
2. Project $[2,1,3]^{\mathsf T}$ onto the span of $[1,0,0]^{\mathsf T}$ and $[0,0,1]^{\mathsf T}$.
3. Apply Gram-Schmidt to $[1,1]^{\mathsf T}$ and $[1,0]^{\mathsf T}$.
4. Form the normal equations for a given $4\times2$ system.
5. State the reduced QR dimensions for an $8\times3$ matrix.

## Coding Questions

1. Verify an orthonormal basis with `Q.T @ Q`.
2. Fit a line using `np.linalg.lstsq`.
3. Solve the same fit using `np.linalg.qr`.
4. Compare residuals from both methods.
