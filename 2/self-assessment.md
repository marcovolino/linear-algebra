---
layout: lesson
title: Self Assessment
module: 2
lesson: 6
lesson_order: 70
duration_minutes: 35
prerequisites:
  - Vectors
  - Vector operations
  - Dot product
learning_outcomes:
  - Check vector magnitude calculations.
  - Practise vector addition and scalar multiplication.
  - Normalise a vector to obtain a unit vector.
  - Check dot product, angle, and projection calculations.
---

Attempt each question before opening the solution.

## Question 1

Compute the magnitude of

$$
\mathbf{v} =
\begin{bmatrix}
4 \\
1 \\
3
\end{bmatrix}.
$$

<details>
  <summary>Show solution</summary>

$$
\lVert \mathbf{v} \rVert_2
= \sqrt{4^2 + 1^2 + 3^2}
= \sqrt{16 + 1 + 9}
= \sqrt{26}
\approx 5.10.
$$
</details>

## Question 2

Compute $\mathbf{x} = \mathbf{v} + \mathbf{w}$, where

$$
\mathbf{v} =
\begin{bmatrix}
1 \\
2 \\
3
\end{bmatrix},
\qquad
\mathbf{w} =
\begin{bmatrix}
4 \\
5 \\
6
\end{bmatrix}.
$$

<details>
  <summary>Show solution</summary>

$$
\mathbf{x} =
\begin{bmatrix}
1 + 4 \\
2 + 5 \\
3 + 6
\end{bmatrix}
=
\begin{bmatrix}
5 \\
7 \\
9
\end{bmatrix}.
$$
</details>

## Question 3

Compute $\mathbf{x} = 2\mathbf{v}$, where

$$
\mathbf{v} =
\begin{bmatrix}
2 \\
4 \\
3
\end{bmatrix}.
$$

<details>
  <summary>Show solution</summary>

$$
2\mathbf{v}
=
2
\begin{bmatrix}
2 \\
4 \\
3
\end{bmatrix}
=
\begin{bmatrix}
4 \\
8 \\
6
\end{bmatrix}.
$$
</details>

## Question 4

Find the unit vector in the direction of

$$
\mathbf{v} =
\begin{bmatrix}
4 \\
2 \\
4
\end{bmatrix}.
$$

<details>
  <summary>Show solution</summary>

$$
\lVert \mathbf{v} \rVert_2 =
\sqrt{4^2 + 2^2 + 4^2}
= \sqrt{36}
= 6.
$$

$$
\mathbf{u}
= \frac{\mathbf{v}}{\lVert \mathbf{v} \rVert_2}
= \frac{1}{6}
\begin{bmatrix}
4 \\
2 \\
4
\end{bmatrix}
=
\begin{bmatrix}
0.667 \\
0.333 \\
0.667
\end{bmatrix}.
$$
</details>

## Question 5

Compute the dot product $\mathbf{v}\cdot\mathbf{w}$, where

$$
\mathbf{v} =
\begin{bmatrix}
2 \\
-1 \\
3
\end{bmatrix},
\qquad
\mathbf{w} =
\begin{bmatrix}
4 \\
0 \\
5
\end{bmatrix}.
$$

<details>
  <summary>Show solution</summary>

$$
\mathbf{v}\cdot\mathbf{w}
= 2(4) + (-1)(0) + 3(5)
= 23.
$$
</details>

## Question 6

Find the scalar projection of

$$
\mathbf{v} =
\begin{bmatrix}
3 \\
4
\end{bmatrix}
$$

onto the unit vector

$$
\mathbf{u} =
\begin{bmatrix}
1 \\
0
\end{bmatrix}.
$$

<details>
  <summary>Show solution</summary>

Because $\mathbf{u}$ is a unit vector, the scalar projection is

$$
\mathbf{v}\cdot\mathbf{u}
= 3(1) + 4(0)
= 3.
$$

The vector projection is

$$
(\mathbf{v}\cdot\mathbf{u})\mathbf{u}
=
3
\begin{bmatrix}
1 \\
0
\end{bmatrix}
=
\begin{bmatrix}
3 \\
0
\end{bmatrix}.
$$
</details>

## Summary

If these questions feel comfortable, move on to matrices. If not, revisit vector notation, magnitude, dot products, and projections before continuing.
