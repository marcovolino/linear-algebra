---
layout: lesson
title: Self Assessment
module: 6
lesson: 5
lesson_order: 270
duration_minutes: 40
prerequisites:
  - Column and row spaces
  - Null space
  - Rank-nullity
  - Rectangular systems
learning_outcomes:
  - Identify matrix subspaces.
  - Compute rank and nullity.
  - Interpret measurement redundancy and ambiguity.
  - Classify rectangular systems.
---

Attempt each question before opening the solution.

## Question 1

For an $m\times n$ matrix, where do its column space and null space live?

<details><summary>Show solution</summary>

The column space is a subspace of $\mathbb{R}^m$. The null space is a subspace of $\mathbb{R}^n$.
</details>

## Question 2

The echelon form of a matrix has pivots in columns $1$ and $3$. Which columns provide a basis for its column space?

<details><summary>Show solution</summary>

Columns $1$ and $3$ of the original matrix, not the echelon form, provide a basis.
</details>

## Question 3

A $4\times7$ matrix has rank $3$. Find its nullity.

<details><summary>Show solution</summary>

Rank-nullity gives

$$
\operatorname{nullity}(A)=7-3=4.
$$
</details>

## Question 4

What does a non-zero vector $\mathbf{z}\in\operatorname{Null}(A)$ imply about two inputs $\mathbf{x}$ and $\mathbf{x}+\mathbf{z}$?

<details><summary>Show solution</summary>

They produce the same output because

$$
A(\mathbf{x}+\mathbf{z})=A\mathbf{x}+A\mathbf{z}=A\mathbf{x}.
$$
</details>

## Question 5

Can an underdetermined consistent system have a unique solution?

<details><summary>Show solution</summary>

No. When $m<n$, rank is less than $n$, so nullity is positive. A consistent system therefore has free variables and infinitely many solutions.
</details>

## Question 6

Why might an overdetermined system have no exact solution?

<details><summary>Show solution</summary>

Noise or contradictory measurements can place $\mathbf{b}$ outside the column space of $A$. Least squares then finds the closest attainable output.
</details>
