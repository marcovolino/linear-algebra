---
layout: page
title: Vectors
---
Vectors are the fundamental objects of linear algebra. They allow us to describe motion, forces, data, images, signals, geometric transformations, and entire systems of equations in a unified mathematical language.

A vector is simply an ordered list of numbers, but with a crucial structure:
these numbers behave collectively under the two operations of addition and scalar multiplication.


### What Is a Vector?
A vector in $$ℝ^n$$ is an ordered list of $$\symbf{n}$$ real numbers. 

A vector is commonly denoted as a **bold** lower-case letter, _e.g._  $$\symbf{v}$$, or a lower-case letter with an arrow above it, _e.g._ $$\vec{v}$$. The scalar components of an N-dimensional vector are commonly denoted as lower-case letters with an integer subscript denoting its position in the vector e.g. $$v_1$$, $$v_2$$, ... $$v_N$$, 

Within this course a vector, and its associated components, are denoted as follows:

$$
\symbf{v} = \begin{bmatrix}
    v_1 \\
    v_2 \\
    \vdots \\
    v_N
\end{bmatrix}
$$

#### Different ways to understand a vector

**Geometric view**:
Vectors can also be interpreted geometrically

<script type="text/tikz">
\begin{tikzpicture}
\draw[help lines, color=gray!30, dashed] (-4.9,-4.9) grid (4.9,4.9);
\draw[->,ultra thick] (-5,0)--(5,0) node[right]{$x$};
\draw[->,ultra thick] (0,-5)--(0,5) node[above]{$y$};
\draw[->,ultra thick, blue] (0,0)--(4,3) node[right]{$v$};
\end{tikzpicture}
</script>

**Algebraic view**:
A list of numbers we can add and scale according to precise rules.

**Data view**:
A structured collection of measurements, e.g., temperature, intensity, features of an image.

**Functional view**
A vector represents a state of a system, a set of coefficients, or a point in parameter space.


