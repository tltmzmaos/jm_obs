---
title: <%tp.file.title%>
tags:
  - DeepLearningAI
  - MachineLearningSpecialization
---
# Reinforcement Learning
* x -> y
	* x: reward or the reward function
	* positive reward / negative reward
## Applications
* Controlling robots
* Factory optimization
* Financial (stock) trading
* Playing games (including video games)
# Mars rover example
![[Pasted image 20240415201205.png]]
# The return in reinforcement learning
* Return = $R_1+rR_2+r^2R_3+...$ (until terminal state)
* Discount Factor: $r = 0.9$
	* $0 + (0.9)0 + (0.9)^20 + (0.9)^3100$
* The return depends on the actions you take
![[Pasted image 20240415201830.png]]
# Making decisions: Policies in reinforcement learning
## Policy
* A policy is a function mapping from states to actions, that tells you what action to take in a given state
	* $\pi(s) = a$
	* $\pi$ : policy
	* $s$ : state
	* $a$ : action
## The goal of reinforcement learning
* Find a policy $\pi$ that tells you what action $(a = \pi(s))$ to take in every state $s$ so as to maximize the return
# Review of key concepts
![[Pasted image 20240415202252.png]]
## Markov Decision Process (MDP)
![[Pasted image 20240415202331.png]]
