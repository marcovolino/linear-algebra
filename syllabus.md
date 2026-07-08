---
layout: page
title: Syllabus
---

The course contains twelve modules, progressing from vectors and matrices to applied computer vision, machine learning, and graphics. Each technical module includes practice exercises and a self-assessment.

<div class="module-list">
{% for module in site.data.modules %}
<section>
  <h2>Module {{ module.number }}: {{ module.title }}</h2>
  <p>{{ module.summary }}</p>
  <ul>
  {% for lesson in module.lessons %}
    <li><a href="{{ lesson.url | relative_url }}">{{ lesson.title }}</a></li>
  {% endfor %}
  </ul>
</section>
{% endfor %}
</div>

## Course Modules

1. Why Linear Algebra?
2. Vectors and Geometry
3. Matrices and Linear Transformations
4. Solving Linear Systems
5. Vector Spaces, Span, Basis, and Dimension
6. Rank, Column Space, and Null Space
7. Orthogonality and Least Squares
8. Eigenvalues and Eigenvectors
9. Singular Value Decomposition
10. Linear Algebra for Computer Vision
11. Linear Algebra for Machine Learning
12. Linear Algebra for Computer Graphics
