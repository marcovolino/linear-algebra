---
layout: lesson
title: Rank and Rank-Nullity
module: 6
lesson: 3
lesson_order: 250
duration_minutes: 50
prerequisites:
  - Column space
  - Null space
learning_outcomes:
  - Compute rank from pivots.
  - Define nullity.
  - Apply the rank-nullity theorem.
  - Interpret rank as retained information.
---

## Rank

The rank of a matrix is the dimension of its column space:

$$
\operatorname{rank}(A)=\dim(\operatorname{Col}(A)).
$$

It also equals the dimension of the row space and the number of pivots in an echelon form.

## Rank-Nullity

If $A$ has $n$ columns, then

$$
\operatorname{rank}(A)+\operatorname{nullity}(A)=n,
$$

where

$$
\operatorname{nullity}(A)=\dim(\operatorname{Null}(A)).
$$

Every input direction is therefore accounted for as either a retained independent direction or a direction lost in the null space.

## Worked Example

Suppose a $3\times5$ matrix has three pivots. Then

$$
\operatorname{rank}(A)=3,
\qquad
\operatorname{nullity}(A)=5-3=2.
$$

The transformation accepts five-dimensional inputs, produces outputs in a three-dimensional column space, and loses two independent input directions.

## Full Rank

An $m\times n$ matrix has full rank when

$$
\operatorname{rank}(A)=\min(m,n).
$$

Full column rank means independent columns and a trivial null space. Full row rank means every vector in $\mathbb{R}^m$ is a possible output.

## Implementation

```python
import numpy as np

A = np.array([[1, 0, 1], [0, 1, 1]], dtype=float)
rank = np.linalg.matrix_rank(A)
nullity = A.shape[1] - rank

print("rank:", rank)
print("nullity:", nullity)
```

{% include callout.html
   type="application"
   title="Compression"
   content="A low-rank data matrix can be represented using fewer independent directions. Later, singular value decomposition will turn this observation into a practical compression method."
%}

## Practice

1. Find the rank and nullity of a $4\times6$ matrix with three pivots.
2. Can a $3\times5$ matrix have rank $4$?
3. What does full column rank imply about $A\mathbf{x}=\mathbf{0}$?

## Summary

Rank counts independent output directions; nullity counts lost input directions. Rank-nullity balances the two against the input dimension.
