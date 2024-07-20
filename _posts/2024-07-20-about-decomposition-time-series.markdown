---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Decomposition_Time_Series
title: About decomposition time series
# title: About decomposition time series
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
date: 2024-07-20 09:00:00 +0900
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

## This is an article about decomposed time series.

hello!

Today we will learn about decomposed time series.

Decomposed time series analysis is a method of decomposing time series data into trend, seasonality, cycle, and random factor (Error) and analyzing each component.

We will explain the decomposition time series below.

{:data-align="center"}

<!-- outline-end -->

## Purpose of decomposed time series analysis

### Understanding the components:

Understand the characteristics and volatility of trends, seasonality, cycles, and random factors that make up time series data.

### Building a prediction model

Each component is analyzed to build a predictive model and use it to predict future values.

### Understand the characteristics of your data

By identifying the characteristics of data, we understand trends and cycles and analyze changes according to trends.

## Types of decomposed time series analysis

### Additive Model

A method of decomposing a time series into the sum of trend, seasonality, cycle, and random factors, expressed as Y(t) = T(t) + S(t) + C(t) + E(t).

### Multiplicative Model

A method of decomposing a time series into the product of trend, seasonality, cycle, and random factors, expressed as Y(t) = T(t) _ S(t) _ C(t) `*` E(t).

## Steps of decomposition time series analysis

### Visualization of time series data

Identify patterns of trends, seasonality, cycles, and random factors in time series data.

### Trend estimation

Estimate long-term trends from time series data.

### Seasonality estimation

Infer seasonal patterns from time series data.

### Cycle estimation

Estimate long-term periodic elements from time series data.

### Random factor (Error) analysis

Analyzes fluctuations other than trends, seasonality, and cycles.

## uses

### Understand the characteristics of time series data

Understand the structure of data by identifying the characteristics of data trends, seasonality, cycles, and random factors.

### Building a prediction model

It is used to analyze each component to predict future values ​​and build a predictive model.

## Conclusion

Decomposed time series analysis is an important technique for identifying and predicting patterns and structures of time series data, and is actively used in various fields.

thank you!
