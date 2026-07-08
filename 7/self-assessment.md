---
layout: lesson
title: Self Assessment
module: 7
lesson: 5
lesson_order: 320
duration_minutes: 40
prerequisites:
  - Orthonormal sets
  - Gram-Schmidt
  - Least squares and QR
learning_outcomes:
  - Check orthonormality and projections.
  - Apply Gram-Schmidt.
  - Interpret least-squares residuals.
  - Use QR factorisation.
---

Attempt each question before opening the solution.

## Question 1

Are $2^{-1/2}[1,1]^{\mathsf T}$ and $2^{-1/2}[1,-1]^{\mathsf T}$ orthonormal?

<details><summary>Show solution</summary>
Yes. Their dot product is zero and each has norm one.
</details>

## Question 2

Project $[2,3,4]^{\mathsf T}$ onto the span of $[1,0,0]^{\mathsf T}$ and $[0,1,0]^{\mathsf T}$.

<details><summary>Show solution</summary>
The spanning vectors are orthonormal, so the projection is $[2,3,0]^{\mathsf T}$.
</details>

## Question 3

In Gram-Schmidt, why is the projection onto earlier vectors subtracted?

<details><summary>Show solution</summary>
It removes components in directions already represented, leaving a vector orthogonal to all earlier basis vectors.
</details>

## Question 4

What condition does a least-squares residual satisfy?

<details><summary>Show solution</summary>
It is orthogonal to the column space: $A^{\mathsf T}\mathbf{r}=\mathbf{0}$.
</details>

## Question 5

If $A=QR$, which system produces the least-squares solution?

<details><summary>Show solution</summary>
Solve the upper-triangular system $R\widehat{\mathbf{x}}=Q^{\mathsf T}\mathbf{b}$.
</details>
