---
layout: lesson
title: Self Assessment
module: 12
lesson: 5
lesson_order: 600
duration_minutes: 35
prerequisites: [2D and 3D transformations, View and projection matrices, Graphics transformation pipeline]
learning_outcomes: [Check transformation composition., Interpret homogeneous coordinates., Trace the camera pipeline., Transform normals.]
---

Attempt each question before opening the solution.

## Question 1
Which transform acts first in $R S\mathbf{x}$?
<details><summary>Show solution</summary>$S$ acts first for column-vector conventions.</details>

## Question 2
Why does a direction use homogeneous coordinate zero?
<details><summary>Show solution</summary>It prevents the translation column from affecting the direction.</details>

## Question 3
What does $PVM$ map?
<details><summary>Show solution</summary>It maps object-space homogeneous vertices into clip coordinates.</details>

## Question 4
How are normals transformed under non-uniform scale?
<details><summary>Show solution</summary>By the inverse transpose of the linear transform, followed by normalisation.</details>
