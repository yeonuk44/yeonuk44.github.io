---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_The_Concept_And_Type_Of_Optimizer
title: About the concept and type of optimizer
# title: About the concept and type of optimizer
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: DB
# multiple tag entries are possible
tags: [db]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-09-15 09:00:00 +0900
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

## This article examines the concept and type of optimizer.

Hello!

The database optimizer is responsible for optimizing user-written queries in the database to establish the most efficient action plan.

This improves the performance of the database and reduces the execution time of queries.

Now, let's talk about the concepts and types of optimizers.

{:data-align="center"}

<!-- outline-end -->

## Concept of Optimizer

Optimizers are responsible for determining the best way to run database queries.

Analyze user-created queries and develop action plans to find the most efficient way to retrieve and manipulate data from the database.

This optimizes the performance of the database and provides quick and accurate results for users.

### Types of Optimizer

There are two main types of optimizers: Rule-based optimizer and Cost-based optimizer.

- **Rule-based Optimizer**:
  - Rule-based optimizers establish action plans according to predefined rules for user-created queries.
  - Because the query is handled according to predefined rules, it can be effective for simple queries, but it can be difficult to establish an optimal action plan for complex queries.
- **Cost-based optimizer**:
  - A cost-based optimizer generates a variety of actionable action plans and calculates the estimated cost for each action plan to select the most efficient action plan.
  - You can establish a more accurate and optimized action plan by taking into account factors such as the statistics of the query and the presence or absence of an index.

### Utilization of Optimizer

- **Improve performance**: Optimizer can be used to improve database performance. Choose the best action plan to speed up query execution and reduce database load.
- **Automated Optimization**: Optimizer lets you automate the optimization of queries, allowing users to write queries without having to worry about the complex task of developing an action plan.

## at the end of the day

Optimizers are key features responsible for optimizing queries in databases, with two types: rule-based optimizers and cost-based optimizers.

Each optimizer has advantages and disadvantages and can be selected and used to improve the performance of the database.

Thank you!
