---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Distance_Measurement_And_Hierarchical_Cluster_Analysis
title: About Distance Measurement and Hierarchical Cluster Analysis
# title: About Distance Measurement and Hierarchical Cluster Analysis
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
date: 2024-07-30 09:00:00 +0900
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

## This article examines distance measurements and hierarchical cluster analysis.

Hello!

Today, we will learn about distance measurements and hierarchical cluster analysis.

{:data-align="center"}

<!-- outline-end -->

### Distance Measure

An important factor used to measure similarity between data in cluster analysis.

It is utilized to determine the similarity between clusters in cluster analysis algorithms by calculating the distance between data.

Typical street measures include Euclid Street, Manhattan Street, and cosine similarity.

#### Euclid Street

A method of calculating the distance of a straight line between data points, suitable for continuous variables.

#### Manhattan Street

A method of calculating vertical and horizontal distances between data points, suitable for continuous variables.

#### Cosine similarity

It is a method of measuring similarity using the angle between vectors, which is suitable for text data or sparse data.

#### Conclusion

It is important to select a distance measure that fits the characteristics and purpose of the data, as the shape and outcome of the cluster can vary depending on the distance measure selected.

#### Hierarchical clustering

Hierarchical cluster analysis is a method of presenting data in a hierarchical structure by grouping them sequentially or in combination.

There is a way to group the given data sequentially according to the distance, or to group all the data into one cluster and group the most similar data sequentially.

A dendrogram is a visual representation of the results of hierarchical cluster analysis and is used to identify the similarity of data and the structure between clusters.

Hierarchical cluster analysis can visually identify similarities between clusters and is useful for understanding hierarchical structures between data.

### at the end of the day

These distance measurements and hierarchical cluster analysis are important methods for measuring similarity between data and forming clusters based on them, and it is important to select them appropriately for the characteristics and purpose of the data.

Thank you!
