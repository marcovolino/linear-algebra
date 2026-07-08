---
layout: lesson
title: Gaussian Elimination
module: 4
lesson: 2
lesson_order: 140
duration_minutes: 50
prerequisites:
  - Linear systems and matrix form
learning_outcomes:
  - Apply the three elementary row operations.
  - Use pivots to eliminate variables.
  - Solve a system by back substitution.
  - Explain why row operations preserve solutions.
---

## Motivation

Gaussian elimination replaces a system with simpler equivalent systems until the unknowns can be recovered from the final rows upward.

## Elementary Row Operations

The allowed operations are:

1. Swap two rows.
2. Multiply a row by a non-zero scalar.
3. Add a multiple of one row to another row.

These operations preserve the solution set because they only reorder equations or replace an equation with an equivalent combination.

## Worked Example

Start with

$$
\left[
\begin{array}{cc|c}
1&1&5\\
2&-1&1
\end{array}
\right].
$$

Eliminate the entry below the first pivot using $R_2\leftarrow R_2-2R_1$:

$$
\left[
\begin{array}{cc|c}
1&1&5\\
0&-3&-9
\end{array}
\right].
$$

The second row gives $-3y=-9$, so $y=3$. Back substitution into $x+y=5$ gives $x=2$.

## Algorithm

For each pivot column:

1. Select a non-zero pivot, swapping rows when necessary.
2. Eliminate entries below the pivot.
3. Continue with the smaller lower-right part of the matrix.
4. Use back substitution after reaching upper-triangular form.

{% include callout.html
   type="note"
   title="Pivoting"
   content="Numerical software usually chooses a large available pivot. This reduces rounding error and avoids division by values close to zero."
%}

## Implementation

```python
import numpy as np

A = np.array([[1.0, 1.0], [2.0, -1.0]])
b = np.array([5.0, 1.0])

factor = A[1, 0] / A[0, 0]
A[1] = A[1] - factor * A[0]
b[1] = b[1] - factor * b[0]

y = b[1] / A[1, 1]
x = (b[0] - A[0, 1] * y) / A[0, 0]
print(x, y)
```

## Common Mistakes

- Applying an operation to the coefficients but not the right-hand side.
- Dividing by a zero pivot instead of swapping rows.
- Stopping after elimination without back substitution.

## Practice

1. Solve $x+2y=7$ and $3x-y=7$ by elimination.
2. Explain when a row swap is needed.
3. Verify your answer by multiplying $A\mathbf{x}$.

## Summary

Gaussian elimination uses solution-preserving row operations to expose one variable at a time, followed by back substitution.
