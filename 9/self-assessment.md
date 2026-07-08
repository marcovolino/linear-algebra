---
layout: lesson
title: Self Assessment
module: 9
lesson: 6
lesson_order: 440
duration_minutes: 40
prerequisites:
  - SVD and its geometry
  - Low-rank approximation
  - Pseudoinverse and conditioning
learning_outcomes:
  - Interpret SVD factors.
  - Reason about rank and approximation.
  - Use the pseudoinverse.
  - Assess numerical sensitivity.
---

Attempt each question before opening the solution.

## Question 1

In $A=U\Sigma V^{\mathsf T}$, what do the columns of $V$ represent?

<details><summary>Show solution</summary>
They are orthonormal input directions, called right singular vectors.
</details>

## Question 2

How is rank read from the singular values?

<details><summary>Show solution</summary>
Rank is the number of non-zero singular values, using an appropriate numerical tolerance in computation.
</details>

## Question 3

Why is truncated SVD useful for image compression?

<details><summary>Show solution</summary>
It retains the strongest rank-one image components while storing far fewer values than the full pixel matrix.
</details>

## Question 4

What solution does $A^+\mathbf{b}$ select for a consistent underdetermined system?

<details><summary>Show solution</summary>
It selects the exact solution with minimum Euclidean norm.
</details>

## Question 5

A matrix has singular values $100$ and $0.01$. What is its condition number?

<details><summary>Show solution</summary>
The condition number is $100/0.01=10000$, indicating strong sensitivity.
</details>
