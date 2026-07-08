---
layout: lesson
title: Orthogonal and Orthonormal Sets
module: 7
lesson: 1
lesson_order: 280
duration_minutes: 45
prerequisites:
  - Dot products and projections
  - Basis and coordinates
learning_outcomes:
  - Test vectors for orthogonality and orthonormality.
  - Explain why non-zero orthogonal vectors are independent.
  - Compute coordinates in an orthonormal basis.
  - Project onto an orthonormal subspace.
---

## Orthogonal Sets

Vectors are orthogonal when their dot product is zero. A set is orthogonal when every distinct pair is orthogonal, and orthonormal when every vector also has unit length.

Non-zero orthogonal vectors are automatically independent. If

$$
c_1\mathbf{q}_1+\cdots+c_k\mathbf{q}_k=\mathbf{0},
$$

dotting with $\mathbf{q}_j$ isolates $c_j\lVert\mathbf{q}_j\rVert^2=0$.

## Orthonormal Coordinates

For an orthonormal basis $\{\mathbf{q}_1,\ldots,\mathbf{q}_n\}$,

$$
\mathbf{x}=\sum_{i=1}^{n}(\mathbf{q}_i^{\mathsf T}\mathbf{x})\mathbf{q}_i.
$$

Coordinates require only dot products. If $Q$ has the basis vectors as columns, then

$$
[\mathbf{x}]_{\mathcal Q}=Q^{\mathsf T}\mathbf{x}.
$$

## Projection

The projection onto the span of orthonormal columns of $Q$ is

$$
\operatorname{proj}_{W}(\mathbf{x})=QQ^{\mathsf T}\mathbf{x}.
$$

For $\mathbf{q}_1=[1,0,0]^{\mathsf T}$ and $\mathbf{q}_2=[0,1,0]^{\mathsf T}$, projecting $[2,3,4]^{\mathsf T}$ gives $[2,3,0]^{\mathsf T}$.

## Implementation

```python
import numpy as np

Q = np.array([[1, 0], [0, 1], [0, 0]], dtype=float)
x = np.array([2, 3, 4], dtype=float)

print(Q.T @ Q)
print(Q @ Q.T @ x)
```

## Practice

1. Are $[1,1]^{\mathsf T}$ and $[1,-1]^{\mathsf T}$ orthogonal?
2. Normalise them to form an orthonormal basis.
3. Project $[4,2,5]^{\mathsf T}$ onto the $xy$-plane.

## Summary

Orthonormal bases combine independence with simple coordinates and projections, making them valuable in geometry and numerical computation.
