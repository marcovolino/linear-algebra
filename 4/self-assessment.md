---
layout: lesson
title: Self Assessment
module: 4
lesson: 5
lesson_order: 170
duration_minutes: 40
prerequisites:
  - Linear systems
  - Gaussian elimination
  - Echelon forms
  - NumPy solving
learning_outcomes:
  - Check matrix representations of systems.
  - Perform elimination and back substitution.
  - Classify solution sets.
  - Select an appropriate numerical solver.
---

Attempt each question before opening the solution.

## Question 1

Write $2x-3y=4$ and $x+y=5$ as $A\mathbf{x}=\mathbf{b}$.

<details>
  <summary>Show solution</summary>

$$
\begin{bmatrix}2&-3\\1&1\end{bmatrix}
\begin{bmatrix}x\\y\end{bmatrix}
=
\begin{bmatrix}4\\5\end{bmatrix}.
$$
</details>

## Question 2

Solve $x+y=6$ and $2x-y=3$ by elimination.

<details>
  <summary>Show solution</summary>

Apply $R_2\leftarrow R_2-2R_1$:

$$
\left[\begin{array}{cc|c}1&1&6\\0&-3&-9\end{array}\right].
$$

Thus $y=3$, and back substitution gives $x=3$.
</details>

## Question 3

Classify the system whose echelon form is

$$
\left[\begin{array}{ccc|c}1&0&2&4\\0&1&-1&3\\0&0&0&0\end{array}\right].
$$

<details>
  <summary>Show solution</summary>

There are three variables but only two pivots. The third variable is free, so the system has infinitely many solutions.
</details>

## Question 4

What does the row $[\,0\ \ 0\mid7\,]$ mean?

<details>
  <summary>Show solution</summary>

It represents $0=7$, a contradiction. Therefore the system has no solution.
</details>

## Question 5

Why should `np.linalg.solve(A, b)` usually be preferred to `np.linalg.inv(A) @ b`?

<details>
  <summary>Show solution</summary>

A direct solve avoids explicitly constructing the inverse, requiring less work and usually producing a more accurate numerical result.
</details>

## Question 6

How can you check a computed solution $\widehat{\mathbf{x}}$?

<details>
  <summary>Show solution</summary>

Compute the residual

$$
\mathbf{r}=\mathbf{b}-A\widehat{\mathbf{x}}.
$$

Then inspect $\lVert\mathbf{r}\rVert_2$ or use `np.allclose(A @ x, b)`. A small residual indicates that the computed vector closely satisfies the equations.
</details>
