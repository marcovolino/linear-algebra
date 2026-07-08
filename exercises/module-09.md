---
layout: page
title: Module 9 Exercises
---

## Concept Questions

1. Why does SVD apply more broadly than eigenvalue decomposition?
2. What geometric information does each singular value carry?
3. Why is truncated SVD an optimal low-rank approximation?
4. How does the pseudoinverse handle null-space ambiguity?
5. What distinguishes conditioning from numerical stability?

## Calculation Questions

1. Find the SVD structure of $\operatorname{diag}(5,2)$.
2. Compute the rank-one expansion of a two-term SVD.
3. Compare full and rank-$10$ storage for a $500\times400$ matrix.
4. Find the pseudoinverse of $\operatorname{diag}(3,0)$.
5. Compute the condition number for singular values $8$, $2$, and $0.5$.

## Coding Questions

1. Reconstruct a matrix from `np.linalg.svd`.
2. Compress a greyscale image with several ranks.
3. Verify a pseudoinverse least-squares solution.
4. Perturb an ill-conditioned system and compare solutions.
