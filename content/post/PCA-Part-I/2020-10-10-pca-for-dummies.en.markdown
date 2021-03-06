---
title: PCA Part I. Intuition
author: 
date: '2021-01-04'
slug: pca_part_1
categories: []
tags:
  - Data Science
subtitle: ''
summary: 'Here is a brief overview on Principal Component Analysis, one of the most popular methods of dimensionality reduction today!'
authors: []
lastmod: '2021-01-02T19:59:31-04:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---
<style>
body {font-size: 80%}
.note{font-size: 10pt;
      line-height: 20pt;
      padding-bottom: 10px}
p{text-indent: 2em;}

details{font-size: 10pt;}
summary{font-size: 100% !important;}
</style>

<div class="note">
<b>DISCLAIMER</b>: This is an introduction into PCA and does not go into depth on the statistics or code. Tread carefully! 
</div>

---

<h3>OVERVIEW</h3>

Principle Component Analysis (PCA) is known for two things: 1) Dimensionality Reduction, and 2) Structure Analysis. Note that it can also be used for **factor extraction**, the first step in Factor Analysis. 

<div class="note">
<b>NOTE</b>: There are plenty of resources online if you wish to learn more about Factor Analysis, but they will not be covered here!
</div>
<br>

<h4>TERMINOLOGY</h4>

So as not to lose anyone, let's define some useful terminology! 
<br><br>

**Features** are what we are measuring. 

<details>
<summary>Example</summary>
<p>Say we have a table with <i>y</i> rows and <i>x</i> columns, then we have <i>x</i> features. Imagine each row being the names of someone you know, and each column measure something distinct about all persons listed (e.g. their height, weight, deepest darkest secrets, etc.). These things we're measuring are the features.</p>
</details>
<br>

**Dimensionality Reduction** is exactly what it sounds like. The goal is to reduce the number of dimensions (i.e. number of features), while retaining useful information from the original data.

<details>
<summary>Example and Enrichment</summary>
<p>Say you wish to visualize your data, in order to get an understanding of the relationships between each feature. However, you have too many features. It becomes impossible to plot them on an x-y graph. How do you visualize this without destroying your computer let alone the laws of physics? Simple, you reduce the number of dimensions to 2. Now, you can plot it on a coordinate plane! </p>

<div class="note">
<b>NOTE</b>: Dimensionality Reduction is different from <i>Feature Selection</i> (e.g. L1 Regularization, L2 Regularization, etc.). The goal of feature selection is to select the most important features. Meanwhile, dimensionality reduction is used to lessen the number of dimensions while capturing the variation in the original data as much as possible.
</div>
</details>
<br>

Given p features, **Principal Components** are the [1, min(n, p)] new variables extracted from n features using Principal Component Analysis. You can think of them as new axes to view the original data. *However, you can no longer interpret the principal components the same way you did with previous features*.
<details>
<summary>Enrichment</summary>
If you have 10 features and you transform them via PCA to get 10 principal components, they are not the same. If you previously had age and weight, now you simply have axes for data points with no interpretable meaning unlike the original variables. With PCA, you may end up with combinations of these variables. Tell me, is there meaning in a new variable that is 30% age and 70% weight?
</details>
<br><br>

<h3>GENERAL IDEA</h3>

To build intuition about what happens in Principal Component Analysis, let's use the graph below as an example. 



<img src="/post/PCA-Part-I/2020-10-10-pca-for-dummies.en_files/figure-html/plot-1.png" width="336" style="display: block; margin: auto;" />

Here, we have 2 features. You can imagine each point representing an observation (e.g. one of your participants). 

When you implement PCA, imagine a line placed at the mean (of all the data points). Imagine rotating it, and every time that you rotate it, it changes how far each observation (i.e. its projection onto the line) point is from the center of the line. This is also called the **squared distances**. And this is what we're trying to *maximize*. 

By doing so, it is as if we are trying to find a line where the observations are farthest from center. Thus, we capture the most amount of variation along this line, and this line is known as a principal component! 


Once again, notice how the features no longer have anything to do with the new axes (principal component). Also notice that if you had 3 or more features, graphing it like we did is no longer possible.

In Part II, we will explore how to do PCA in Python. See you there!


<h3>Additional Resources</h3>

StatQuest has great videos explaining what I mentioned with the graph with more detail! 
