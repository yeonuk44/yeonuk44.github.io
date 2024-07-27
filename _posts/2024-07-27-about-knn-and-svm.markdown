---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_KNN_And_SVM
title: About KNN and SVM
# title: About KNN and SVM
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Statistics
# multiple tag entries are possible
tags: [statistics]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-07-27 09:00:00 +0900
# seo
# if not specified, date will be used.
#meta_modify_date: 2021-08-10 11:32:53 +0900
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

# optional
# please use the "image_viewer_on" below to enable image viewer for individual pages or posts (_posts/ or [language]/_posts folders).
# image viewer can be enabled or disabled for all posts using the "image_viewer_posts: true" setting in _data/conf/main.yml.
#image_viewer_on: true
# please use the "image_lazy_loader_on" below to enable image lazy loader for individual pages or posts (_posts/ or [language]/_posts folders).
# image lazy loader can be enabled or disabled for all posts using the "image_lazy_loader_posts: true" setting in _data/conf/main.yml.
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
#published: false
---

<!-- outline-start -->

## This is an article about KNN and SVM.

Hello!

Today, we will learn about KNN and SVM.

{:data-align="center"}

<!-- outline-end -->

### K-Nearest Neighbors (K-Nearest Neighbors, KNN)

K-nearest neighbor (KNN) is one of the supervised learning algorithms used for classification and regression problems. We will discuss KNNs below.

#### principle of operation

- Neighbor's Choice: Select the K nearest neighbors to the new data point.
- Majority Vote: For classification problems, a majority vote among K neighbors determines the class of new data points. For regression problems, use the average of K neighbors as the predicted value.

#### pros and cons

- Advantages: Simple to implement, fast and intuitive to train.
- The downside: computational costs can be high as the distance to all training data needs to be calculated during the prediction stage.

#### Utilization

- Outlier detection: Can be used for outlier detection.
- Recommendation system: can be used to find similar users or products.

### Support Vector Machine (SVM)

Support Vector Machine (SVM) is a supervised learning algorithm used for classification and regression problems that maps data into high-dimensional spaces to find the optimal decision boundaries.

#### principle of operation

- Find Decision Boundary: Find the best hyperplane to separate the data.
- Find Support Vector: Find the support vector that is the closest data point to the hyperplane.
- Kernel Trick: To solve nonlinear problems, use kernel functions to map data into higher-dimensional spaces.

#### pros and cons

- Advantage: It performs well on high-dimensional data, and can solve nonlinear problems through kernel techniques.
- Disadvantages: the interpretation of the model is difficult, sensitive to data preprocessing and parameter settings.

#### Utilization

- Binary and multi-class classification: widely used for classification problems.
- Outlier detection: Can be used for outlier detection.

### at the end of the day

KNN and SVM are supervised learning algorithms that are useful for various problems based on their respective features.

Thank you!
