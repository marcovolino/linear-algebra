---
layout: lesson
title: Introduction to Linear Algebra
module: 1
lesson: 1
lesson_order: 10
duration_minutes: 25
prerequisites:
  - Algebraic notation
learning_outcomes:
  - Explain why linear algebra is useful in engineering, vision, graphics, and AI.
  - Distinguish scalars, vectors, matrices, and transformations.
  - Recognise images and systems of equations as linear algebra objects.
---

## Motivation

Linear algebra is the mathematics of vectors, matrices, vector spaces, and linear transformations. It gives us a compact way to describe data, geometry, signals, images, systems, and models.

{% include callout.html
   type="application"
   title="Computer vision connection"
   content="A greyscale image can be stored as a matrix of pixel intensities. Transforming, filtering, compressing, and comparing images all rely on matrix and vector operations."
%}

Linear algebra is a powerful tool for modelling and solving problems in science and engineering, including:

- **Computer Graphics**: modelling graphical objects and performing rotations, scaling, and other transformations in 2D and 3D spaces.
- **Engineering**: solving systems of equations that model circuits, structures, controls, and sensor systems.
- **Data Science and Machine Learning**: regression, clustering, dimensionality reduction, embeddings, and neural networks.
- **Physics**: representing states and operators using vectors and matrices.
- **Economics**: modelling systems with multiple variables and constraints.

## Core Objects

A **scalar** is a single number, such as $3.2$, $-1$, or a sensor reading.

A **vector** is an ordered list of numbers:

$$
\mathbf{x} =
\begin{bmatrix}
x_1 \\
x_2 \\
\vdots \\
x_n
\end{bmatrix}.
$$

A **matrix** is a rectangular array of numbers:

$$
A =
\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \cdots & a_{mn}
\end{bmatrix}.
$$

In applications, a vector might represent a point, velocity, feature vector, signal window, or embedding. A matrix might represent an image, dataset, transformation, system of equations, or neural-network layer.

## Worked Example

A colour pixel is often stored as three numbers:

$$
\mathbf{p} =
\begin{bmatrix}
220 \\
120 \\
40
\end{bmatrix},
$$

where the entries represent red, green, and blue intensities. The same vector notation can also describe a 3D point, a velocity, or three measured features. The mathematics is shared even when the interpretation changes.

## Python Preview

```python
import numpy as np

pixel = np.array([220, 120, 40])
brightness = np.linalg.norm(pixel)
print(brightness)
```

## Practice

1. Give one example of a scalar, vector, and matrix from engineering or AI.
2. Explain why an image can be treated as a matrix.
3. Name one task where a matrix might represent a transformation.

## Summary

Linear algebra gives us a language for data and geometry. The next lessons build the vector skills needed for similarity, projections, transformations, and systems of equations.
