---
title: "Predictive e-scooter usage"
date: 2020-12-20
published: true
tags: [dataviz, altair, hvplot, holoviews]
excerpt: "Embedding interactive charts on static pages using Jekyll."
altair-loader:
  altair-chart-1: "charts/measlesAltair.json"
hv-loader:
  hv-chart-1: ["charts/measlesHvplot.html", "500"] # second argument is the height
toc: false
toc_sticky: false
---


## What is the most important feature in escooter usage modeling?

In this post, we run random forest models to forcast seasonal trip counts seperately in Chicago and Austin:

### Compare the feature importance between two cities

- See the [raw source code]([https://raw.githubusercontent.com/MUSA-550-Fall-2021/github-pages-starter/main/_posts/2021-11-29-measles-charts.md](https://raw.githubusercontent.com/MUSA-550-Fall-2022/github-pages-starter/main/_posts/2019-04-13-measles-charts.md)) of this post for details on how these charts were embedded.
- See the [lecture 13A slides](https://github.com/MUSA-550-Fall-2022/week-13/blob/main/lecture-13A.ipynb) for the code that produced these plots.

## What is the relation between features?
 Try k-means clusterig in chicago dataset to see the underlying structure
###  See the difference in cluster

