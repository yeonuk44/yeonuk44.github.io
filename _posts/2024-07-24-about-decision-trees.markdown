---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Decision_Trees
title: About decision trees
# title: About decision trees
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
date: 2024-07-24 09:00:00 +0900
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

## This is an article about decision trees.

hello!

Today we will learn about decision trees.

Decision Tree is one of the supervised learning algorithms used to classify or predict data. It uses a tree structure to classify or predict data according to several rules.

We will explain the decision tree below.

{:data-align="center"}

<!-- outline-end -->

## Main Features

### Tree structure

A decision tree has a tree structure consisting of nodes and edges, and each node classifies or branches data according to specific conditions.

### Rule-based learning

Each node in the tree classifies or predicts data based on specific rules (conditions).

### Ease of interpretation

A decision tree is an intuitive and easy-to-interpret model that makes it easy to visually understand how things are classified based on what conditions.

## How it works

### Select split criteria

When splitting data, choose the best criteria (conditions) to split it into subgroups with the highest purity possible.

### Recursive division

Split the data based on the selected criteria, and continue growing the tree by selecting split criteria again for each subgroup.

### Pruning

Prune the tree at an appropriate level to prevent overfitting and improve generalization ability.

## uses

### Classification problem

Used to predict a categorical target variable. For example, it is used to predict whether a customer will buy a product.

### Regression problem

Used to predict a continuous target variable. For example, it is used to predict house prices.

## Main Algorithm

### Classification and Regression Trees (CART)

It is a decision tree algorithm that can be used for both classification and regression problems.

### ID3(Iterative Dichotomizer 3)

It is an algorithm that divides based on the criterion that maximizes information gain.

## Conclusion

Decision trees have excellent interpretability and are used for classification and prediction problems in a variety of fields.

thank you!
