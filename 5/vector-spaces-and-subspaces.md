---
layout: lesson
title: Vector Spaces and Subspaces
module: 5
lesson: 1
lesson_order: 180
duration_minutes: 45
prerequisites:
  - Vectors and vector operations
  - Linear systems
learning_outcomes:
  - State the essential properties of a vector space.
  - Test whether a subset is a subspace.
  - Recognise common vector and function spaces.
  - Explain why every subspace contains the zero vector.
---

## Motivation

Vectors need not be arrows. Signals, images, polynomials, and feature arrays can all be treated as vectors when addition and scaling behave consistently. A vector space captures those shared rules.

## Vector Spaces

A vector space is a set $V$ whose elements can be added and scaled. The results must remain in $V$, addition must behave normally, and $V$ must contain a zero vector and additive inverses.

For example, $\mathbb{R}^n$ is a vector space. So is the set of all polynomials of degree at most two:

$$
P_2=\{a+bx+cx^2:a,b,c\in\mathbb{R}\}.
$$

## The Subspace Test

A non-empty subset $W$ of a vector space is a subspace when, for all $\mathbf{u},\mathbf{v}\in W$ and scalars $c$:

1. $\mathbf{u}+\mathbf{v}\in W$.
2. $c\mathbf{u}\in W$.

These conditions imply that $\mathbf{0}\in W$.

## Worked Example

Consider

$$
W=\left\{
\begin{bmatrix}x\\y\\z\end{bmatrix}:x+y+z=0
\right\}.
$$

If $\mathbf{u},\mathbf{v}\in W$, the component sum of $\mathbf{u}+\mathbf{v}$ is $0+0=0$. Scaling a vector by $c$ changes its component sum to $c(0)=0$. Therefore $W$ is a subspace of $\mathbb{R}^3$.

By contrast, $x+y+z=1$ does not define a subspace because it excludes the zero vector.

## Application

All images representable as combinations of a fixed set of templates form an image subspace. Restricting analysis to that subspace can reduce storage and suppress irrelevant variation.

## Practice

1. Is the line $y=3x$ a subspace of $\mathbb{R}^2$?
2. Is the line $y=3x+1$ a subspace? Explain.
3. Show that all symmetric $2\times2$ matrices form a subspace.

## Summary

Vector spaces formalise compatible addition and scaling. A subspace is a subset closed under both operations and must pass through the zero vector.
