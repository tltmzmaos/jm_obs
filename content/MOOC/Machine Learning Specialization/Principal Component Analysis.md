---
title: Principal Component Analysis
tags:
  - DeepLearningAI
  - MachineLearningSpecialization
---
# Reducing the number of features
* Commonly used by data scientists to visualize the data, to figure out what might be going on
## Examples
### Car measurements
![[Pasted image 20240414205757.png]]
### From 3D to 2D
![[Pasted image 20240414205849.png]]
### Data visualization
![[Pasted image 20240414210014.png]]
# PCA algorithm
* replaces two features with one feature
![[Pasted image 20240414210236.png]]
* Choose the least different axis
![[Pasted image 20240414210511.png]]
* Coordinate on the new axis: dot product
![[Pasted image 20240414210657.png]]
### More principal components
![[Pasted image 20240414210808.png]]
### PCA is not linear regression
![[Pasted image 20240414210845.png]]
### Approximation to the original data
![[Pasted image 20240414211002.png]]
# PCA in code
Optional pre-processing: Perform feature scaling
* Fit the data to obtain 2 (or 3) new axes (principal components)
* Optionally examine how much variance is explained by each principal component
* Transform (project) the data onto the new axes
![[Pasted image 20240414211404.png]]
![[Pasted image 20240414211424.png]]
### Applications of PCA
* Visualization: reduce to 2 or 3 features
* Less frequently used for
	* Data compression (to reduce storage or transmission costs)
	* Speeding up training of a supervised learning model
