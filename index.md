---
layout: home
title: Introduction
---
This course provides a concise but deep refresher on the core topics of linear algebra used in mathematics, data science, physics, engineering, and computer science.
This course is intended for Undergraduates, Master’s students, and professionals seeking a mathematical refresher.
The course makes use of the following text books with references to related sections that should be consulted for further reading
- Jānis Lazovskis – Introduction to Linear Algebra
- Gilbert Strang – Introduction to Linear Algebra (5th Edition)

## Prerequisite
- Prior exposure to basic linear algebra (not necessarily strong).
- Comfort with algebra and basic calculus notation.
- No programming experience required (tutorials provided).

## Learning Outcomes

By the end of the course, students will be able to:
- **Core Algebraic Skills**
  - Perform vector and matrix operations; compute dot products, projections, and norms.
  - Execute Gaussian elimination; identify REF/RREF; compute inverses when they exist.
  - Calculate determinants and explain their geometric meaning.
  - Solve systems of equations using elimination, matrix methods, and least squares.
- **Conceptual & Geometric Understanding**
  - Interpret linear combinations, span, basis, dimension, and vector spaces.
  - Understand the four fundamental subspaces (Strang’s framework).
  - Visualize orthogonality, projections, and least squares solutions.
- **Advanced Topics**
  - Compute eigenvalues/eigenvectors; diagonalize matrices when possible.
  - Work with symmetric matrices, quadratic forms, and positive definiteness.
  - Understand and apply the Singular Value Decomposition and Principal Component Analysis.
- **Software Skills**
  - Use Python/NumPy for computations (optional but encouraged).
  - Apply code to solve systems, perform least squares, compute eigenvalues, and run PCA.


## Contents - TODO
{% assign pages = site.pages | where_exp: 'page', 'page.title' %}
{% for page in pages %}
- [{{page.title}}]({{site.baseurl}}{{page.url}})
{% endfor %}
