---
layout: lesson
title: Self Assessment
module: 10
lesson: 6
lesson_order: 500
duration_minutes: 40
prerequisites:
  - Image matrices
  - Homogeneous transformations
  - Camera projection
  - Convolution and calibration
learning_outcomes:
  - Reason about image array shapes.
  - Compose geometric transformations.
  - Project 3D points.
  - Interpret filtering and calibration.
---

Attempt each question before opening the solution.

## Question 1

What is the array shape of a $720$-pixel-high, $1280$-pixel-wide RGB image?

<details><summary>Show solution</summary>
Its usual shape is $(720,1280,3)$.
</details>

## Question 2

Why can homogeneous coordinates represent translation with a matrix?

<details><summary>Show solution</summary>
The added coordinate lets translation values occupy an extra matrix column, turning an affine operation into linear multiplication in the enlarged space.
</details>

## Question 3

Project $(X_c,Y_c,Z_c)=(2,1,4)$ with focal length $100$ and principal point $(0,0)$.

<details><summary>Show solution</summary>
$u=100(2/4)=50$ and $v=100(1/4)=25$, so the pixel is $(50,25)$.
</details>

## Question 4

Why is fixed-kernel convolution a linear operation?

<details><summary>Show solution</summary>
Each output is a weighted sum of input pixels, so convolution preserves addition and scalar multiplication.
</details>

## Question 5

What do small singular values of a calibration matrix indicate?

<details><summary>Show solution</summary>
They indicate parameter directions that measurements constrain weakly, making the estimate sensitive to noise.
</details>
