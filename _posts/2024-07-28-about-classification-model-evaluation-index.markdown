---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Classification_Model_Evaluation_Index
title: About the classification model evaluation index
# title: About the classification model evaluation index
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
date: 2024-07-28 09:00:00 +0900
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

## This article examines the classification model evaluation index.

Hello!

Today, we will look at the classification model evaluation index.

There are several indicators for evaluating the performance of classification models.

{:data-align="center"}

<!-- outline-end -->

### Accuracy

Accuracy represents the percentage of all predictions correctly predicted and is calculated as (TP + TN) / (TP + TN + FP + FN).

This represents the percentage of samples that the model correctly predicted; however, it may not be an appropriate indicator for a disproportionate class distribution.

### Precision and Recall

The precision represents the proportion of what the model is actually positively predicted, and is calculated as TP / (TP + FP).

Reproducibility represents the proportion of what the model actually predicts as positive, and is calculated as TP / (TP + FN).

Precision focuses on reducing false positives, while reproducibility focuses on reducing false negatives.

### F1 Score

The F1 score is a harmonic average of precision and reproducibility, calculated as 2* (precision * reproducibility) / (precision + reproducibility).

This is an indicator of whether precision and reproducibility are balanced.

### ROC Curves and AUC

#### ROC(Receiver Operating Characteristic) 곡선

A graph showing the classification performance of the model, which represents the curve of the false positive ratio (FPR) for reproducibility.

#### AUC(Area Under the Curve)

The area under the ROC curve is an indicator of the performance of the model comprehensively.

### Confusion Matrix

The predicted values of the actual class and model in the two-way classification are tabulated and used to evaluate the classification performance of the model in detail by representing TP, TN, FP, and FN.

### Utilization

These evaluation metrics are used to comprehensively evaluate the performance of the model and to understand the performance of each model.

### at the end of the day

It is utilized to accurately evaluate the performance of the model and improve the performance of the model by comprehensively considering the evaluation indicators of the classification model.

Thank you!
