---
title: "Sampling 1"
excerpt: "Starting my journey to log concave sampling"
collection: blog
tags:
  - mathematics
  - machine learning
  - sampling
layout: single
author_profile: true
permalink: /sampling-1/
---

Just a template for now -- will update soon enough


Imagine you want to compute the area under a tricky curve, like \( f(x) = \sin(x^2) \), from \( x = 0 \) to \( x = 1 \). Analytically, it’s a mess. Monte Carlo makes it simple:
1. Generate random points \((x, y)\) in a rectangle containing the curve (e.g., \( x \in [0, 1] \), \( y \in [0, 1] \)).
2. Check if each point lies below the curve (\( y \leq f(x) \)).
3. The fraction of points below the curve, multiplied by the rectangle’s area, approximates the integral.

Mathematically, if you sample \( N \) points and \( M \) fall below the curve, the area is roughly:
\[
\text{Area} \approx \frac{M}{N} \cdot \text{Rectangle Area}
\]
As \( N \) grows, the approximation gets better, thanks to the law of large numbers.

## Why Are They Cool?

Monte Carlo methods shine in high-dimensional problems, like those in machine learning or physics. For example:
- **Bayesian Inference**: Estimating posterior distributions in probabilistic models.
- **Optimization**: Approximating gradients in complex loss landscapes.
- **Physics Simulations**: Modeling particle interactions in statistical mechanics.

The catch? They can be slow to converge (think \( O(1/\sqrt{N}) \) error), but their simplicity and flexibility make them a go-to tool.

## A Fun Example

Suppose you want to estimate \( \pi \) using Monte Carlo. Draw a unit square (\( 1 \times 1 \)) and a quarter-circle inside it (radius 1, centered at \((0, 0)\)). Generate random points in the square and count how many fall inside the quarter-circle. Since the quarter-circle’s area is \( \pi/4 \), the ratio of “hits” to total points, multiplied by 4, approximates \( \pi \):
\[
\pi \approx 4 \cdot \frac{\text{Points inside quarter-circle}}{\text{Total points}}
\]