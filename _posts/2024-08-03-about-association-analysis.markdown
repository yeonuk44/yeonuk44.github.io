---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_The_Association_Analysis
title: About the association analysis
# title: About the association analysis
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
date: 2024-08-03 09:00:00 +0900
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

## This article examines the association analysis.

Hello!

Today, we're going to look at the association analysis.

Association analysis is one of the data mining techniques that discovers interesting relationships between items in large datasets.

This is used for business decision-making by identifying the relevance of products or deriving rules.

We will discuss the association analysis below.

{:data-align="center"}

<!-- outline-end -->

### the main concept

#### Support

Indicates the frequency of the rule's overall appearance, and indicates how many specific sets of items occurred during the entire transaction.

#### Confidence

It represents the probability that A and B will be included simultaneously among the transactions involving A and B, and it represents how strong the relationship between A and B is among the highly supported rules.

#### Elevation (Lift)

It indicates how often the relationship between A and B occurs relative to coincidence, and a greater than 1 indicates a positive correlation between the two items.

### Utilization

#### Product recommendation system

It is used to identify the associations between products and present recommended products to customers.

#### Inventory management

It is used to pre-adjust the inventory of another product when sales of one product increase by identifying the relevance of the product.

### Algorithms

#### Apriori algorithm

It is used to generate association rules by navigating a set of frequent items, and generates rules based on support and reliability.

#### FP-Growth Algorithm

It is used to build a Frequent Pattern Tree (FP-tree) to find frequent patterns and use it to extract frequent item sets.

### Precautions

#### data preprocessing

Pre-processing such as removing noise or outliers is required to improve the quality of data.

#### Pattern Interpretation

Before applying the association rules found to your business, you must carefully examine their implications and validity.

### at the end of the day

Association analysis is a powerful data mining technique that is used in product recommendation, marketing strategy establishment, inventory management, etc. in a variety of fields and provides useful insights for the business by discovering efficient rules.

Thank you!
