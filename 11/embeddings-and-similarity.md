---
layout: lesson
title: Embeddings and Similarity
module: 11
lesson: 3
lesson_order: 530
duration_minutes: 45
prerequisites: [Vectors, Distance and cosine similarity]
learning_outcomes: [Interpret objects as embedding vectors., Compare Euclidean and cosine similarity., Normalise embeddings., Compute nearest neighbours.]
---

## Vector Representations

An embedding maps an object to $\mathbf{x}\in\mathbb{R}^d$. Similar objects should occupy nearby or aligned locations.

Euclidean distance measures separation:

$$
d(\mathbf{x},\mathbf{y})=\lVert\mathbf{x}-\mathbf{y}\rVert_2.
$$

Cosine similarity measures directional alignment:

$$
s(\mathbf{x},\mathbf{y})=
\frac{\mathbf{x}^{\mathsf T}\mathbf{y}}
{\lVert\mathbf{x}\rVert_2\lVert\mathbf{y}\rVert_2}.
$$

For unit-normalised embeddings, maximising cosine similarity is equivalent to minimising Euclidean distance.

```python
import numpy as np

E = np.array([[1, 2], [2, 1], [-1, 0]], dtype=float)
E = E / np.linalg.norm(E, axis=1, keepdims=True)
query = np.array([1, 1], dtype=float)
query /= np.linalg.norm(query)
print(E @ query)
```

## Practice

1. Why can vector magnitude distort Euclidean comparison?
2. Compute cosine similarity for parallel vectors.
3. What must be checked before normalising an embedding?

## Summary

Embeddings turn semantic comparison into geometry; the appropriate metric depends on whether magnitude carries meaning.
