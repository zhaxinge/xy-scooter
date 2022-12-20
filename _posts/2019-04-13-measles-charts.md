---
title: "Predictive e-scooter usage"
date: 2020-12-20
published: true
tags: [dataviz, cluster analysis, hvplot, holoviews]
excerpt: "Understanding the key features which determine e-scooter usage."
hv-loader:
  hv-chart-1: ["charts/austin_import.html", "500"] # second argument is the height
  hv-chart-2: ["charts/chicago_import.html", "500"] 
  hv-chart-3: ["heatmap.html", "500"] 
  hv-chart-4: ["charts/scatter_3d.html", "500"] 
  hv-chart-5: ["charts/scatter_matrix.html", "500"] 
toc: false
toc_sticky: false
---


## What is the most important feature in escooter usage modeling?

In this post, we run random forest models to forcast seasonal trip counts seperately in Chicago and Austin:

### Compare the feature importance between two cities

<div id="hv-chart-1"></div>

<div id="hv-chart-2"></div>

## What is the relation between features?

###  Correlation matrix
 
<div id="hv-chart-3"></div>

###  See the difference in cluster

To test and explore, we run a k means model to determine the clusters inside the data and explore the cluster data characteristics.

<div id="hv-chart-4"></div>

From the model run results and pca analysis, the structure of cluster does exist inside the data, but the number of clusters may be relatively small, about two, in order to better understand the internal data characteristics of the clusters, we set the number of clusters to three, and plot the data of clusters respectively correlation matrix to explore the relationship between the data.

<div id="hv-chart-5"></div>

To test and explore, we run a k means model to determine the clusters inside the data and explore the cluster data characteristics.

From the model run results and pca analysis, the structure of cluster does exist inside the data, but the number of clusters may be relatively small, about two, in order to better understand the internal data characteristics of the clusters, we set the number of clusters to three, and plot the data of clusters respectively correlation matrix to explore the relationship between the data.
