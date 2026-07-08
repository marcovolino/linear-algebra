---
layout: page
title: Module 4 Exercises
---

These exercises support the solving linear systems module.

## Concept Questions

1. What information is stored in an augmented matrix?
2. Why do elementary row operations preserve the solution set?
3. How do pivots distinguish unique and non-unique solutions?
4. What does a contradictory row mean geometrically?
5. Why is a direct numerical solve preferred to matrix inversion?

## Calculation Questions

1. Write $3x+y=8$ and $x-2y=-1$ in matrix form.
2. Solve that system by Gaussian elimination.
3. Reduce the following augmented matrix to echelon form and classify its solutions:
   $$
   \left[
   \begin{array}{cc|c}
   1&2&4\\
   2&4&8
   \end{array}
   \right].
   $$
4. Classify the system represented by
   $$
   \left[
   \begin{array}{cc|c}
   1&-1&2\\
   0&0&5
   \end{array}
   \right].
   $$
5. Parameterise the solutions of $x+2y-3z=6$.

## Coding Questions

1. Solve a $3\times3$ system using `np.linalg.solve`.
2. Verify the result by computing its residual norm.
3. Create a singular system and record the exception raised by NumPy.
4. Fit a line to five noisy points with `np.linalg.lstsq`.

## Application Questions

1. What could an inconsistent calibration system reveal about its measurements?
2. Why might an image reconstruction system have infinitely many solutions?
