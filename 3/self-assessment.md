---
layout: lesson
title: Self Assessment
module: 3
lesson: 5
lesson_order: 120
duration_minutes: 40
prerequisites:
  - Matrices and matrix operations
  - Matrix multiplication
  - Identity, inverse, and transpose
  - Matrices as linear transformations
learning_outcomes:
  - Check matrix arithmetic and dimension calculations.
  - Compute matrix products and transposes.
  - Identify inverse and identity relationships.
  - Interpret matrices as geometric transformations.
---

Attempt each question before opening the solution.

## Question 1

Let

$$
A =
\begin{bmatrix}
1 & -2 \\
3 & 0
\end{bmatrix},
\qquad
B =
\begin{bmatrix}
4 & 1 \\
-1 & 2
\end{bmatrix}.
$$

Compute $2A+B$.

<details>
  <summary>Show solution</summary>

$$
2A+B
=
\begin{bmatrix}
2 & -4 \\
6 & 0
\end{bmatrix}
+
\begin{bmatrix}
4 & 1 \\
-1 & 2
\end{bmatrix}
=
\begin{bmatrix}
6 & -3 \\
5 & 2
\end{bmatrix}.
$$
</details>

## Question 2

If $C$ is $3 \times 2$ and $D$ is $2 \times 4$, which of $CD$ and $DC$ are defined, and what are their dimensions?

<details>
  <summary>Show solution</summary>

The product $CD$ is defined:

$$
(3 \times 2)(2 \times 4) = 3 \times 4,
$$

so $CD$ is $3 \times 4$, while

$$
(2 \times 4)(3 \times 2)
$$

has non-matching inner dimensions. Therefore $DC$ is not defined.
</details>

## Question 3

Compute

$$
\begin{bmatrix}
1 & 2 \\
0 & -1
\end{bmatrix}
\begin{bmatrix}
3 & 1 \\
2 & 4
\end{bmatrix}.
$$

<details>
  <summary>Show solution</summary>

Using row-column dot products,

$$
\begin{bmatrix}
1(3)+2(2) & 1(1)+2(4) \\
0(3)+(-1)(2) & 0(1)+(-1)(4)
\end{bmatrix}
=
\begin{bmatrix}
7 & 9 \\
-2 & -4
\end{bmatrix}.
$$
</details>

## Question 4

Find the transpose of

$$
M =
\begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6
\end{bmatrix}.
$$

<details>
  <summary>Show solution</summary>

Rows become columns:

$$
M^{\mathsf T}
=
\begin{bmatrix}
1 & 4 \\
2 & 5 \\
3 & 6
\end{bmatrix}.
$$
</details>

## Question 5

Find the inverse of

$$
S =
\begin{bmatrix}
4 & 0 \\
0 & 2
\end{bmatrix}.
$$

<details>
  <summary>Show solution</summary>

The inverse reverses each coordinate scaling:

$$
S^{-1}
=
\begin{bmatrix}
\frac{1}{4} & 0 \\
0 & \frac{1}{2}
\end{bmatrix}.
$$

Multiplying $S^{-1}S$ gives the $2 \times 2$ identity matrix.
</details>

## Question 6

Describe the transformation represented by

$$
R =
\begin{bmatrix}
0 & -1 \\
1 & 0
\end{bmatrix},
$$

and compute $R[2,1]^{\mathsf T}$.

<details>
  <summary>Show solution</summary>

$R$ rotates vectors anticlockwise by $90^\circ$. Applying it gives

$$
R
\begin{bmatrix}
2 \\
1
\end{bmatrix}
=
\begin{bmatrix}
-1 \\
2
\end{bmatrix}.
$$
</details>
