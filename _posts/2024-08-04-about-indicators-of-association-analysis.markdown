---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_The_Indicators_Of_Association_Analysis
title: About the indicators of association analysis
# title: About the indicators of association analysis
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
date: 2024-08-04 09:00:00 +0900
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

## This article examines the indicators of association analysis.

Hello!

Today, we're going to look at the indicators of association analysis.

Association analysis uses a variety of indicators to assess the association between products and derive rules.

Below, we will describe the indicators that are mainly used in association analysis.

{:data-align="center"}

<!-- outline-end -->

### Support

An indicator of how often a particular set of items occurs during the entire transaction.

Support is defined as follows.

Support = (number of transactions involving a specific set of items) / (total number of transactions)

### Confidence

An indicator of the reliability of a rule, which refers to the conditional probability that A and B will be included simultaneously in a transaction containing A.

Reliability is defined as follows.

Reliability = (number of transactions involving A and B) / (number of transactions involving A)

### Elevation (Lift)

It is an indicator of how strong the relationship between the two products is compared to coincidence.

Enhancements are defined as follows.

'Advanced = (Support) / (Support for A \* Support for B) '

### Lift (Leverage)

An indicator of the difference between the expected number of transactions and the actual number of transactions when the two items are independent.

The lift is defined as follows.

'Lift = (number of transactions including A and B) - (A's approval rating \* B's approval rating)'

### Utilization

These indicators are used to measure the association between products and to discover useful rules.

For example, a highly reliable rule can be interpreted as having a strong relationship between products, and when the lift is greater than 1, it shows a stronger relationship than a coincidence.

### at the end of the day

In association analysis, these various indicators are comprehensively used to discover meaningful rules and use them for business decision-making.

Thank you!
