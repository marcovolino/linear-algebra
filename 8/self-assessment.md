---
layout: lesson
title: Self Assessment
module: 8
lesson: 6
lesson_order: 380
duration_minutes: 40
prerequisites:
  - Eigenpairs and characteristic equations
  - Diagonalisation
  - Stability and symmetric matrices
learning_outcomes:
  - Verify and compute eigenpairs.
  - Interpret diagonalisation and matrix powers.
  - Analyse stability.
  - Apply the spectral theorem.
---

Attempt each question before opening the solution.

## Question 1

Verify that $[1,1]^{\mathsf T}$ is an eigenvector of $\begin{bmatrix}3&1\\1&3\end{bmatrix}$.

<details><summary>Show solution</summary>
Multiplication gives $[4,4]^{\mathsf T}=4[1,1]^{\mathsf T}$, so the eigenvalue is $4$.
</details>

## Question 2

Find the eigenvalues of $\begin{bmatrix}2&0\\0&5\end{bmatrix}$.

<details><summary>Show solution</summary>
The characteristic equation is $(2-\lambda)(5-\lambda)=0$, so the eigenvalues are $2$ and $5$.
</details>

## Question 3

What makes a matrix diagonalizable?

<details><summary>Show solution</summary>
An $n\times n$ matrix is diagonalizable when it has $n$ linearly independent eigenvectors.
</details>

## Question 4

What happens to a dynamical mode with eigenvalue $-0.6$?

<details><summary>Show solution</summary>
Its sign alternates while its magnitude decays toward zero because $\lvert-0.6\rvert<1$.
</details>

## Question 5

State the spectral theorem for real symmetric matrices.

<details><summary>Show solution</summary>
Every real symmetric matrix has real eigenvalues and an orthonormal eigenvector basis, so it can be written $A=QDQ^{\mathsf T}$.
</details>
