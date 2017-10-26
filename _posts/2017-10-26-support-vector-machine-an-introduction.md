---
layout: post
published: true
mathjax: true
featured: false
comments: true
title: Support Vector Machine - An Introduction
description: An introduction to SVM
headline: Support Vector Machine - An Introduction
categories:
  - MachineLearning
tags: Coursera MachineLearning
---
>&quot;Imagination is more important than knowledge. Knowledge is limited. Imagination encircles the world.&quot;
><small><cite title="Einstein">Einstein</cite></small>

## Support Vector Machine
SVM is an alternative view for logistic regression. Starting from logistic regression we can derive a good understanding of basic SVM.

![svm_formula.png]({{site.baseurl}}/images/posts/SupportVectorMachine_AnIntroduction/svm_formula.png)

Also helpfull is the concept of **large margins** or **decision boundaries** to help understand what SVM's are doing under the hood.

### SVM Decision Boundary
$$min\, C \sum_{i=1}^{m}\left[ y^{(i)} cost_1(\theta^T x^{(i)}) + (1-y^{(i)} cost_0(\theta^T x^{(i)})\right] + \frac{1}{2}\sum_{i=1}^n \theta_j^2$$

## Kernels
![kernel_landmarks.png]({{site.baseurl}}/images/posts/SupportVectorMachine_AnIntroduction/kernel_landmarks.png)

###But How To Get Those Landmarks?
The training example are exactly the landmarks with the corresponding values (0 or 1) to which category they belong to.

Given example *x*: <br>
$$ f_1 = similarity(x,l^{(1)})$$ <br>
$$ f_2 = similarity(x,l^{(2)})$$ <br>
... <br>

In a **Gaussian Kernel** similarity corresponds to: $$ exp\left(-\frac{\Vert x - l^{(i)}\Vert^2}{2\sigma^2}\right)$$

All the $$f_{(i)}$$ are grouped for each training example $$(x^{(i)}, y^{(i)}) in a feature vector $$f^{(i)}$$ with the first entry $$f_0^{(i)} = 1$$.

**Hypothesis**:<br>
Given $$x$$, compute features $$f \in \mathbb{R}^{m+1}$$ <br>
	Predict $$y=1$$ if $$\theta^{T}f \ge 0$$
    
**Training**:<br>
$$min\, C \sum_{i=1}^{m}\left[ y^{(i)} cost_1(\theta^T x^{(i)}) + (1-y^{(i)} cost_0(\theta^T x^{(i)})\right] + \frac{1}{2}\sum_{i=1}^n \theta_j^2$$