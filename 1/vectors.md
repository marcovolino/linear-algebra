---
layout: post
title: Vectors
---
A vector is a mathematical object that consists of both a magnitude and direction. 
Vectors can be used to represent quantaties that have these two characteristics, such as force and velocity. 
Vectors can be interpreted 


### Definitions and Notation
A vector is commonly denoted as a **bold** lower-case letter, _e.g._  $$\symbf{v}$$, or a lower-case letter with an arrow above it, _e.g._ $$\vec{v}$$. The scalar components of an N-dimensional vector are commonly denoted as lower-case letters with an integer subscript denoting its position in the vector e.g. $$v_1$$, $$v_2$$, ... $$v_N$$, 

Within this document a vector and its associated components are denoted as:

$$
\symbf{v} = \begin{bmatrix}
    v_1 \\
    v_2 \\
    \vdots \\
    v_N
\end{bmatrix}
$$




The magnitude of a vector is denoted 
$$
|\symbf{v}|
$$,and is computed as follows:

$$
|\symbf{v}| = \sqrt{v_1^2 + v_2^2 + \dots + v_N^2}
$$

or more generally expressed as 

$$
|\symbf{v}| = \sqrt{\sum_{n=1}^{N}{v_n^2}}
$$



#### Geometric interpretation of vectors

Vectors can also be interpreted geometricall

<script type="text/tikz">
\begin{tikzpicture}
\draw[help lines, color=gray!30, dashed] (-4.9,-4.9) grid (4.9,4.9);
\draw[->,ultra thick] (-5,0)--(5,0) node[right]{$x$};
\draw[->,ultra thick] (0,-5)--(0,5) node[above]{$y$};
\draw[->,ultra thick, blue] (0,0)--(4,3) node[right]{$v$};
\end{tikzpicture}
</script>


### Unit Vectors


Unit vectors 

$$
\symbf{u} = \frac{\symbf{v}}{|\symbf{v}|} 
$$


## Vector Operations

### Addition and Subtraction
Vectors can be added and subtracted from one another as follows:

$$
\symbf{v} \pm \symbf{w}  = \begin{bmatrix}
    v_1 \pm w_1 \\
    v_2 \pm w_2 \\
    \vdots \\
    v_N \pm w_N
\end{bmatrix}
$$

- Vector addition is commutative $$ \symbf{v} + \symbf{w} = \symbf{w} + \symbf{v}$$
- Vector subtraction is not commutative $$ \symbf{v} - \symbf{w} \neq \symbf{w} - \symbf{v}$$

### Scalar Multiplication
Lets say we want to multiply our vector, $$\symbf{v}$$, by the scalar value $$s$$, in this case each component of the vector is multipled by a factor $$s$$.

$$
s\symbf{v}  = \begin{bmatrix}
    sv_1 \\
    sv_2 \\
    \vdots \\
    sv_N
\end{bmatrix}
$$


### Linear Combination


$$ c\symbf{v} + d\symbf{w}$$










## Vector Spaces


### Definition and properties.

### Subspaces, span, and linear combinations.


### Basis and dimension.







## Worked Problems

**1. Compute the magnitude of the following vector** $$ \symbf{v} = \begin{bmatrix}
   4 \\
    1 \\
    3
\end{bmatrix}
$$
<details>
  <summary><a>Click here for solution</a></summary>
$$|\symbf{v}| = \sqrt{4^2 + 1^2 + 3^2} = \sqrt{16 + 1 + 9} = \sqrt{26} = 5.1 $$ 
</details>
<br>

**2. Compute the resulting vector $$\symbf{x} = \symbf{v} + \symbf{w}$$, where** $$ \symbf{v} = \begin{bmatrix}
   1 \\
    2 \\
    3
\end{bmatrix}
\symbf{w} = \begin{bmatrix}
   4 \\
    5 \\
    6
\end{bmatrix}
$$
<details>
  <summary><a>Click here for solution</a></summary>
$$ \begin{bmatrix}
   1 \\
    2 \\
    3
\end{bmatrix}
+
\begin{bmatrix}
   4 \\
    5 \\
    6
\end{bmatrix}
=
\begin{bmatrix}
   5 \\
    7 \\
    9
\end{bmatrix}
$$</details>
<br>
 
**3. Compute the resulting vector $$\symbf{x} = 2\symbf{v} $$, where** $$ \symbf{v} = \begin{bmatrix}
   2 \\
    4 \\
    3
\end{bmatrix}
$$
<details>
  <summary><a>Click here for solution</a></summary>
$$ 2\begin{bmatrix}
   2 \\
    4 \\
    3
\end{bmatrix}
=
\begin{bmatrix}
   4 \\
    8 \\
    6
\end{bmatrix}
$$</details>
<br>


**3. Given a vector $\symbf{v}=$, compute the resulting unit vector, where** 
$$ \symbf{v} = \begin{bmatrix}
   4 \\
    2 \\
    4
\end{bmatrix}
$$
<details>
  <summary><a>Click here for solution</a></summary>
$$ |\symbf{v}| = \sqrt{4^2 + 2^2 + 4^2} = \sqrt{16+4+16} = \sqrt{36} = 6$$
$$ \symbf{u} = \frac{\symbf{v}}{\symbf{|v|}} = \frac{1}{6}\begin{bmatrix}
   4 \\
    2 \\
    4
\end{bmatrix} = \begin{bmatrix}
   0.667 \\
    0.333 \\
    0.667
\end{bmatrix}$$
</details>
<br>
