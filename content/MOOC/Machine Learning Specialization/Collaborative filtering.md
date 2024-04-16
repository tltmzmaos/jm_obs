---
title: Collaborative filtering
tags:
  - DeepLearningAI
  - MachineLearningSpecialization
---
# Making recommendations
* Not every user rate every movie and it's important for the system to know which users have rated which movies
* one possible way to approach the problem is to look at the movies that users have not rated
![[Pasted image 20240415203056.png]]
# Using per-item feature
![[Pasted image 20240415203454.png]]
## Cost function
#### Notation
* $r(i,j) = 1$ if user $j$ has rated movie $i$ (0 otherwise)
* $y^{(i,j)}$ = rating given by user $j$ on movie $i$ (if defined)
* $w^{(j)}, b^{(j)}$ = parameters for user $j$
* $x^{(i)}$ = feature vector for movie $i$
* For user $j$ and movie $i$, predict rating: $w^{(j)} \cdot x^{(i)} + b^{(j)}$
* $m^{(j)}$ = number of movies rated by user $j$
* To learn $w^{(j)},b^{(j)}$:
	* $n$ = number of features
$$
min_{w^{(j)}b^{(j)}} J(w^{(j)}, b^{(j)}) = \frac{1}{2m^{(j)}} \sum_{i:r(i,j)=1} (w^{(j)} \cdot x^{(i)} + b^{(j)} - y^{(i,j)})^2 + \frac{\mu}{2m^{(j)}} \sum_{k=1}^{n}(w_k^{(j)})^2
$$
$$
\frac{1}{2} \sum_{i:r(i,j)=1} (w^{(j)} \cdot x^{(i)} + b^{(j)} - y^{(i,j)})^2 + \frac{\mu}{2} \sum_{k=1}^{n}(w_k^{(j)})^2
$$

* To learn parameters $w^{(1)},b^{(1)},...w^{(n_u)},b^{(n_u)}$  for all users:
	* $f(x) = w^{(j)} \cdot x^{(i)} + b^{(j)}$
$$
J \binom{w^{(1)},...,w^{(n_u)}}{b^{(1)},...,b^{(n_u)}} = \frac{1}{2} \sum_{j=1}^{n_u} \sum_{i:r(i,j)=1} (w^{(j)} \cdot x^{(i)} + b^{(j)} - y^{(i,j)})^2 + \frac{\mu}{2} \sum_{j=1}^{n_u} \sum_{k=1}{n}(w_k^{(j)})^2
$$

# Collaborative filtering algorithm
![[Pasted image 20240415205150.png]]
![[Pasted image 20240415205236.png]]
## Gradient Descent
![[Pasted image 20240415205259.png]]
