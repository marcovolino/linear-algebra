---
layout: page
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
