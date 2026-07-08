---
layout: lesson
title: Self Assessment
module: 5
lesson: 5
lesson_order: 220
duration_minutes: 40
prerequisites:
  - Vector spaces and subspaces
  - Span and independence
  - Basis and dimension
learning_outcomes:
  - Test subspaces and span membership.
  - Identify dependent vector sets.
  - Find basis coordinates.
  - Determine dimensions.
---

Attempt each question before opening the solution.

## Question 1

Is $W=\{[x,y]^{\mathsf T}:y=2x\}$ a subspace of $\mathbb{R}^2$?

<details><summary>Show solution</summary>

Yes. Every vector has the form $x[1,2]^{\mathsf T}$, so $W$ is the span of one vector and is closed under addition and scaling.
</details>

## Question 2

Is $[3,5]^{\mathsf T}$ in the span of $[1,1]^{\mathsf T}$ and $[1,2]^{\mathsf T}$?

<details><summary>Show solution</summary>

Solve $c_1+c_2=3$ and $c_1+2c_2=5$. This gives $c_2=2$ and $c_1=1$, so the vector is in the span.
</details>

## Question 3

Are $[1,0,1]^{\mathsf T}$, $[0,1,1]^{\mathsf T}$, and $[1,1,2]^{\mathsf T}$ independent?

<details><summary>Show solution</summary>

No. The third vector equals the sum of the first two, so the set is dependent.
</details>

## Question 4

Find the coordinates of $[7,1]^{\mathsf T}$ in the basis $\mathcal B=\{[1,1]^{\mathsf T},[1,-1]^{\mathsf T}\}$.

<details><summary>Show solution</summary>

Solving $c_1+c_2=7$ and $c_1-c_2=1$ gives $c_1=4$, $c_2=3$. Thus $[\mathbf{x}]_{\mathcal B}=[4,3]^{\mathsf T}$.
</details>

## Question 5

What is the dimension of the subspace of $\mathbb{R}^3$ spanned by $[1,0,0]^{\mathsf T}$ and $[0,1,0]^{\mathsf T}$?

<details><summary>Show solution</summary>

The vectors are independent, so they form a basis for their span. Its dimension is $2$.
</details>
