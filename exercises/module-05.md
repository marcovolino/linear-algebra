---
layout: page
title: Module 5 Exercises
---

These exercises support the vector spaces, basis, and dimension module.

## Concept Questions

1. Why must every subspace contain the zero vector?
2. How does span differ from linear independence?
3. Why does every vector have unique coordinates in a basis?
4. What does dimension measure?

## Calculation Questions

1. Test whether $\{[x,y]^{\mathsf T}:x-y=0\}$ is a subspace.
2. Determine whether $[2,3,5]^{\mathsf T}$ lies in the span of $[1,0,1]^{\mathsf T}$ and $[0,1,1]^{\mathsf T}$.
3. Test whether $[1,2]^{\mathsf T}$ and $[3,6]^{\mathsf T}$ are independent.
4. Find a basis for the plane $x+y+z=0$.
5. Find the coordinates of $[5,3]^{\mathsf T}$ in the basis $\{[1,1]^{\mathsf T},[1,-1]^{\mathsf T}\}$.

## Coding Questions

1. Use `np.linalg.lstsq` and a residual check to test span membership.
2. Use `np.linalg.matrix_rank` to test column independence.
3. Reconstruct a vector from its coordinates in a non-standard basis.

## Application Questions

1. How can a basis reduce the storage required for signals?
2. What does linear dependence among dataset features reveal?
