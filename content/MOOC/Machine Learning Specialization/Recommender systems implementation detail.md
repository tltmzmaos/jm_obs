---
title: Recommender systems implementation detail
tags:
  - DeepLearningAI
  - MachineLearningSpecialization
---
# Mean normalization
![[Pasted image 20240415205525.png]]
![[Pasted image 20240415205630.png]]
# TensorFlow implementation of collaborative filtering
![[Pasted image 20240415205730.png]]
* Derivatives
![[Pasted image 20240415205750.png]]
* Gradient Descent
![[Pasted image 20240415205816.png]]
# Finding related items
* The features $x^{(i)}$ of item $i$ are quite hard to interpret
* To find other items related to it, find item $k$ with $x^{(k)}$ similar to $x^{(i)}$
	* $\sum_{l=1}^{n}(x_l^{(k)}-x_l^{(i)})^2$
	* $||x^{(k)}-x^{(i)}||^2$
	* ex) with smallest distance
## Limitations of Collaborative Filtering
* Cold start problem. How to
	* rank new items that few users have rated?
	* show something reasonable to new users who have rated few items?
* Use side information about items or users:
	* Item: Genre, movie stars, studio, ...
	* User: Demographics (age, gender, location), expressed preferences, ...