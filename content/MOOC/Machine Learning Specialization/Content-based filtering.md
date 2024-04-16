---
title: Content-based filtering
tags:
  - DeepLearningAI
  - MachineLearningSpecialization
---
# Collaborative filtering vs Content-based filtering
## Collaborative filtering
Recommend items to you based on ratings of uses who gave similar ratings as you
## Content-based filtering
recommend items to you based on the features of use and item to find good match (requires having some features of each user)
### Examples
> [!info] Vector space can be different

User features - $X_u^{(j)}$ for user $j$ 
* Age
* Gender
* Country
* Movies watched
* Average rating per genre
Movie feature - $X_m^{(i)}$ for movie $i$ 
* Year
* Genre/Genres
* Reviews
* Average rating
### Learning to match
Predict rating of user $j$ on movie $i$ as
$$
w^{(j)}\cdot x^{(i)} + b^{(j)} = V_u^{(j)} \cdot V_m^{(i)}
$$
$V_u^{(j)}$ computed from $x_u^{(j)}$
$V_m^{(i)}$ computed from $x_m^{(i)}$

The size should match

# Deep learning for content-based filtering
* A good way to develop a content-based filtering algorithm is to use deep learning.
![[Pasted image 20240414123853.png]]
![[Pasted image 20240414123929.png]]
* $v_u^{(i)}$ is a vector of length 32 that describes user j with features $x_u^{(j)}$
* $v_m^{(i)}$ is a vector of length 32 that describes movie i with features $x_m^{(i)}$
* To find movies similar to movie i
	* fined smallest distance: $||V_m^{(k)}-V_m^{(i)}||^2$ 
	* With Collaborative filtering: $||X^{(k)}-X^{(i)}||$ 
* This can be pre-computed ahead of time

# Recommending from a large catalogue
### Two steps: Retrieval & Ranking
* Retrieval
	* Generate large list of plausible item candidates
		* e.g.
			* For each of the last 10 movies watched by the user, find 10 most similar movies $||V_m^{(k)}-V_m^{(i)}||^2$
		* For most viewed 3 genres, find the top 10 movies
		* Top 20 movies in the country
	* Combine retrieved items into list, removing duplicates and items already watched/purchased
* Rankings
	* Take list retrieved and rank using learned model
	* Display ranked items to user
### Retrieval step
* Retrieving more items results in better performance, but slower recommendations
* To analyze/optimize the trade-off, carry out offline experiments to see if retrieving additional items results in more relevant recommendations

# Ethical use of recommender systems
### What is the goal of the recommender system?
* Movies most likely to be rated 5 stars by user
* Products most likely to be purchased
* Ads most likely to be clicked on
* Products generating the largest profit
* Video leading to maximum watch time
### Ethical considerations with recommender systems
#### Positive case
* Travel industry
	* Good travel experiences to more users
	* More profitable
	* Bid higher for ads
* Payday loans
	* Squeeze customers more
	* More profit
	* Bid higher for ads
* Amelioration: Do not accept ads from exploitative businesses
#### Problematic cases
* Maximizing user engagement has led to large social media/video sharing sites to amplify conspiracy theories and hate/toxicity
	* Amelioration: Filter out problematic content such as hate speech, fraud, scams and violent content
* Can a ranking system maximize your profit rather than user's welfare be presented in a transparent way?
	* Amelioration: Be transparent with users

# TensorFlow implementation of content-based filtering
![[Pasted image 20240414163005.png]]
