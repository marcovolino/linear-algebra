---
layout: page
title: Vector Operations
---
Having introduced vectors as ordered lists of numbers representing points, directions, or data, we now develop the algebra of vectors, the operations that make vector spaces meaningful.


## Addition and Subtraction

Given two vectors in $$𝑅^n$$:

$$\symbf{v}  = \begin{bmatrix}
    v_1 \\
    v_2 \\
    \vdots \\
    v_n
\end{bmatrix}
\symbf{w}  = \begin{bmatrix}
    w_1 \\
    w_2 \\
    \vdots \\
    w_n
\end{bmatrix}
$$

their addition is defined componentwise:

$$
\symbf{v} \pm \symbf{w}  = \begin{bmatrix}
    v_1 + w_1 \\
    v_2 + w_2 \\
    \vdots \\
    v_N + w_N
\end{bmatrix}
$$

Vector addition is commutative $$\symbf{v} + \symbf{w} = \symbf{w} + \symbf{v}$$

**Geometric Interpretation**
In $$𝑅^2$$ or $$𝑅^3$$, Place the tail of $$\symbf{w}$$ at the head of \symbf{v}. The diagonal from the start of 
\symbf{v} to the head of \symbf{w} is \symbf{v+w}.


<script type="text/tikz">
\begin{tikzpicture}
\draw[help lines, color=gray!30, dashed] (-4.9,-4.9) grid (4.9,4.9);
\draw[->,ultra thick] (-5,0)--(5,0) node[right]{$x$};
\draw[->,ultra thick] (0,-5)--(0,5) node[above]{$y$};
\draw[->,ultra thick, blue] (0,0)--(3,1) node[midway,below,sloped]{$v$};
\draw[->,ultra thick, green] (3,1)--(4,3) node[midway,below,sloped]{$w$};
\draw[->,ultra thick, red] (0,0)--(4,3) node[right]{$v+w$};
\end{tikzpicture}
</script>



## Scalar Multiplication
Lets say we want to multiply our vector, $$\symbf{v}$$, by the scalar value $$s$$, in this case each component of the vector is multipled by a factor $$s$$.

$$
s\symbf{v}  = \begin{bmatrix}
    sv_1 \\
    sv_2 \\
    \vdots \\
    sv_N
\end{bmatrix}
$$

## Linear Combination

$$ c\symbf{v} + d\symbf{w}$$
