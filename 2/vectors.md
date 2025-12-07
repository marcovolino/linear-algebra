---
layout: page
title: Vectors
---
Vectors are the fundamental objects of linear algebra. They allow us to describe motion, forces, data, images, signals, geometric transformations, and entire systems of equations in a unified mathematical language.

A vector is simply an ordered list of numbers, but with a crucial structure:
these numbers behave collectively under the two operations of addition and scalar multiplication.


### What Is a Vector?
A vector in $$ℝ^n$$ is an ordered list of $$\symbf{n}$$ real numbers. 

A vector is commonly denoted as a **bold** lower-case letter, _e.g._  $$\symbf{v}$$, or a lower-case letter with an arrow above it, _e.g._ $$\vec{v}$$. The scalar components of an N-dimensional vector are commonly denoted as lower-case letters with an integer subscript denoting its position in the vector e.g. $$v_1$$, $$v_2$$, ... $$v_N$$. Within this course a vector, and its associated components, are denoted as follows:

$$
\symbf{v} = \begin{bmatrix}
    v_1 \\
    v_2 \\
    \vdots \\
    v_N
\end{bmatrix}
$$

### Different ways to understand a vector
- **Geometric view**:
Vectors can also be interpreted geometrically

<script type="text/tikz">
\begin{tikzpicture}
\draw[help lines, color=gray!30, dashed] (-4.9,-4.9) grid (4.9,4.9);
\draw[->,ultra thick] (-5,0)--(5,0) node[right]{$x$};
\draw[->,ultra thick] (0,-5)--(0,5) node[above]{$y$};
\draw[->,ultra thick, blue] (0,0)--(4,3) node[right]{$v$};
\end{tikzpicture}
</script>

- **Algebraic view**:
A list of numbers we can add and scale according to precise rules.

- **Data view**:
A structured collection of measurements, e.g., temperature, intensity, features of an image.

- **Functional view**
A vector represents a state of a system, a set of coefficients, or a point in parameter space.

### Row vs Column Notation
Vectors are traditionally written as columns:

$$
\symbf{v} = \begin{bmatrix}
    v_1 \\
    v_2 \\
    v_3
\end{bmatrix}
$$

Writing as rows,

$$
\symbf{v}^T = 
\begin{bmatrix} 
    v_1 & v_2 & v_3
\end{bmatrix}
$$

is simply a transposed form used in dot products and matrix multiplication.

*Important: A row vector is not the same mathematical object as a column vector,  their shapes carry meaning in linear algebra.*

### The Zero Vector and Direction
The zero vector is:

$$
\symbf{v} = 
\begin{bmatrix} 
    0 & 0 & \cdots & 0
\end{bmatrix}
$$

and behaves like the number 0 in ordinary arithmetic.
Every nonzero vector $$\symbf{v}$$ has:
- a direction (the orientation of the arrow)
- a magnitude or length




### Vector Spaces as the Natural Home of Vectors
A set of vectors forms a vector space when:

- You can add any two vectors and stay inside the set.
- You can multiply any vector by a scalar and stay inside the set.

Examples:
- $$ℝ^2$$, $$ℝ^3$$, $$ℝ^n$$
- The set of all polynomials of degree ≤ 3
- The set of all continuous functions
- All $$ m×n matrices $$

Later in the course, we will formalise this.


### Vectors as Points and Arrows
In $$ℝ^2$$, a vector like

$$
\symbf{v} = 
\begin{bmatrix} 
    3 \\ 
    2
\end{bmatrix}
$$

Corresponds to:
- the point (3,2)
- the arrow from (0,0) to (3,2)

In $$ℝ^3$$, 

$$
\symbf{v} = 
\begin{bmatrix} 
    1 \\ 
    -2 \\
    4
\end{bmatrix}
$$

is a point in 3D space and an arrow from the origin.

**Key idea:** The location of the arrow is irrelevant, only its direction and magnitude matter.
Sliding vectors around while keeping them parallel and the same length does not change the vector.
This abstraction is central to linear algebra.


### Vectors Beyond Geometry
Even though we can draw only 2D and 3D vectors, vectors in higher dimensions behave the same.

Examples of higher-dimensional vectors:
- A grayscale image with 1,000 pixels → a vector in $$ℝ^1000$$.
- A dataset with 20 features → each data point is a vector in $$ℝ^20$$.
- A sound clip sampled at 44,100 Hz for 1 second → a vector in $$ℝ^44100$$.

### Coordinate Axes and Basis Vectors
The standard basis vectors in $$ℝ^n$$ are:

$$ \symbf{e}_1 = \begin{bmatrix} 1 & 0 & \cdots & 0 \end{bmatrix} $$
$$ \symbf{e}_2 = \begin{bmatrix} 0 & 1 & \cdots & 0 \end{bmatrix} $$ 
$$ \symbf{e}_n = \begin{bmatrix} 0 & 0 & \cdots & 1 \end{bmatrix} $$ 

Every vector can be written uniquely as:

$$ \symbf{v} = v_1\symbf{e}_1 + v_2\symbf{e}_2 + \cdots + v_n\symbf{e}_n $$

This representation is foundational because:
- it shows linear algebra is about combining building blocks,
- later modules will change the basis to simplify problems,
- coordinate-free interpretations become possible.

### Motivation: Why Study Vectors?
Vectors allow us to express:
1. **Geometry**:  Points, lines, planes, higher-dimensional objects
2. **Physics**: Forces, velocities, electric fields, acceleration.
3. **Data Science and Machine Learning**: Every data sample is a vector. Every model parameter set is a vector. Algorithms manipulate vectors and matrices at scale.
4. **Systems of Equations**: A system such as $$x + 2y + 3z = 6$$ is reinterpreted as a dot product $$\begin{bmatrix} 1 & 2 & 3 \end{bmatrix} \dot \begin{bmatrix} x & y & z \end{bmatrix} = 6$$
5. **Computer Graphics**: Coordinates, transformations, rotations, scaling.

In short: vectors are the universal format for structured numerical information.



