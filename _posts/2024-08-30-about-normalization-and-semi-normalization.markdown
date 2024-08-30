---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Normalization_And_Semi_Normalization
title: About Normalization and Semi-Normalization
# title: About Normalization and Semi-Normalization
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
date: 2024-08-30 09:00:00 +0900
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

## This is an article about normalization and semi-normalization.

Hello!

Today, we learned about regularization and semi-regularization!

{:data-align="center"}

<!-- outline-end -->

## Normalization

Normalization is a process used in database design to minimize redundancy and to maintain data consistency.

The main goal is to eliminate data duplication and prevent anomalies that can occur when inserted, updated, or deleted.

### Goals

1. Minimize data duplication: One data must be stored in one location.
2. Data Dependency Management: It should be easy to modify or delete data by minimizing dependencies between tables in the database.
3. Prevent insertion, update, and deletion anomalies: Avoid anomalies (update anomalies, insertion anomalies, deletion anomalies) that can occur when data is inserted, updated, or deleted.

### the normalization process

1. 1st Normalization (1NF): All property values must be atomic.
2. 2nd Normalization (2NF): Remove partial functional dependencies so that all properties must be fully functional dependencies on the candidate key.
3. 3rd Normalization (3NF): Remove transitional functional dependencies so that all properties are not transitional functional dependencies on candidate keys.
4. Voice-Code Normalization (BCNF): All determinants must be candidate keys.

## Denormalization

Semi-normalization is the process of reassembling normalized tables to improve the performance of a database.

It is primarily used in read operations-intensive online analytical processing (OLAP) environments, increasing data duplication and reassembling some normalized tables.

### Goals

1. Improved lookup performance: The process of putting regularized tables back together improves the speed of lookup operations.
2. Reduce response time: Reduce response time when running complex queries on large databases.
3. Save storage space: Save storage space for redundant data and optimize database capacity.

### a semi-normalization method

1. Combining tables: Reunite normalized tables to optimize lookup operations.
2. Add duplicate data to speed up lookup operations by adding duplicate data.
3. Add Calculated Fields: Pre-calculates, stores, and uses data that requires complex operations.

## at the end of the day

Normalization and semi-normalization are the two main strategies for minimizing duplication of data and improving the performance of databases in database design.

Normalization is used to maintain data consistency and minimize data redundancy, and semi-normalization is the process of recombining data to improve the performance of lookup operations.

When designing a database, it is important to optimize the performance of the database by properly combining normalization and semi-normalization.

Thank you!
