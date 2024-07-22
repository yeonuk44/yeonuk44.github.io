---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Data_Division
title: About data division
# title: About data division
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
date: 2024-07-22 09:00:00 +0900
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

## This is an article about data division.

hello!

Today we will learn about data division.

Data partitioning is an important step in machine learning and statistical modeling. It refers to the process of dividing given data for training, validation, and testing.

We will explain data partitioning below.

{:data-align="center"}

<!-- outline-end -->

## Purpose of data division

### Model training

Provides training data to learn the model.

### Model validation

Provides validation data to evaluate model performance.

### Model testing

Provides test data to evaluate the generalization ability of the model.

## Types of data division

### Training Data

This is the data used to train the model and is used to adjust the model's parameters.

### Validation Data

This is data for evaluating model performance and tuning hyperparameters, and is used to verify performance after training the model.

### Test Data

It is used to evaluate the generalization ability of a model and determines how well the model performs on data it is not seeing for the first time.

## How to split data

### Holdout method

This is the most basic method of dividing data into learning, verification, and testing at a certain rate.

### Cross-Validation

This is a method of evaluating a model by dividing the data into multiple folds and performing cross-validation. It is used to prevent overfitting and evaluate the stability of the model.

## caution

### Data consistency

When partitioning data, care must be taken to ensure that the same data samples are not duplicated in different subsets.

### Data distribution

The data for training, validation, and testing must be split so that it well represents the characteristics of the entire data.

## uses

### Model evaluation

It is used to evaluate and compare the performance of learned models.

### Hyperparameter tuning

It is utilized to tune hyperparameters to optimize model performance.

## Conclusion

Data partitioning is an important step in appropriately dividing data for model training, validation, and testing. It plays an important role in evaluating the model's generalization ability and increasing model reliability.

thank you!
