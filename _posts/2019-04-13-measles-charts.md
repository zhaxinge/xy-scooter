---
title: "Predictive e-scooter usage"
date: 2020-12-20
published: true
tags: [dataviz, cluster analysis, hvplot, holoviews]
excerpt: "Understanding the key features which determine e-scooter usage."
hv-loader:
  hv-chart-1: ["charts/austin_import.html", "500"] # second argument is the height
  hv-chart-2: ["charts/chicago_import.html", "500"] 
  hv-chart-3: ["charts/heatmap.html", "500"] 
  hv-chart-4: ["charts/scatter_3d.html", "500"] 
  hv-chart-5: ["charts/scatter_matrix.html", "500"] 
toc: false
toc_sticky: false
---


## What is the most important feature in escooter usage modeling?

In this post, we run random forest models to forcast seasonal trip counts seperately in Chicago and Austin. By using this model, we can quickly derive the degree of contribution of all variables to the model, and help us determine the key variables that affect the trip count prediction, of course, this can only be used as a rough estimate because what affects the feature importance is not only the feature. And this can only be used as a rough estimate because what affects the importance of the feature is not only the correlation between the feature itself and the dependent variable but also the quality of the feature data.

### Compare the feature importance between two cities

#### Feature importance of Random Forest Model in Austin 
<div id="hv-chart-1"></div>

```python

Training Score = 0.974186720753059
Test Score = 0.8680791745734173

```

#### Feature importance of Random Forest Model in Chicago 
<div id="hv-chart-2"></div>

```python

Training Score = 0.9887343942665165
Test Score = 0.9595406262241419

```

Based on the best accuracy of the model, we conducted iteration by grid search and derived the final feature importance results from the best-performing model. From the results of the two models, we can see that for Austin, the most important predictors include: `start hour`, `trip duration`, `income`, `distance to school`, and `employed ratio`, and for Chicago, the most important predictor variables include: `crash count`, `start hour`, `family type`, `trip duration`, `distance to school`.

Among all the predictors, people’s use of scooters is most likely to be related to the length of the trip and travel time. It is worth noticng that in Chicago, people are very concerned about whether it is safe to use a scooter in the place of travel, and the importance of this feature in Austin is not particularly important, which may be due to the better traffic environment in Austin than in Chicago, or the relatively uniform distribution of crashes, but this point does not prove the relationship between crash counts and people's scooter use. 

## What is the relation between features?

###  Correlation matrix
 
<div id="hv-chart-3"></div>

From the correlation matrix above, we can see apart from employed rate and income, there is no severe correlation between features. And when we plot the scatter plot of these two features. We can notice that these two variables do have a non-linear positive correlation.

![emploted_ratiovsincom]({{ site.url }}{{ site.baseurl }}/assets/images/emploted_ratiovsincom.png)

###  See the difference in cluster

To test and explore, we run a k means model to determine the clusters inside the data structure and explore the cluster data characteristics.

First, we set the number of clusters to three,and see the difference in depedent variables:

```python

da.groupby('category').mean()['count']

category
0     72.393602
1    164.710220
2    314.256158
Name: count, dtype: float64

```
Obviously the three clusters have different escooter usage characteristics. In addition to the dependent variable, do the other features within the cluster have different characteristics? In the further steps we run a PCA analysis.

<div id="hv-chart-4"></div>

From the model run results and PCA analysis, the structure of cluster does exist inside the data, but the number of clusters may be relatively small, about two to three, in order to better understand the internal data characteristics of the clusters, and plot some scatter plot to explore the relationship between the features.

### Scatter plots of distance features by cluster category label

<div id="hv-chart-5"></div>

From the above figure, we can see that the difference between the data classified as 1 and the data classified as 0 and 2 is not obvious, except for the data classified as 1 and the data classified as 0 and 2, which means that the census tract in the training set of this data can be roughly divided into two classes. In addition,  although the distribution range of the three clusters are similar, the relationship between the variables does differ, which means that we can try to classify census tract with the cluster method, and get the most likely to use scooter regional features.


