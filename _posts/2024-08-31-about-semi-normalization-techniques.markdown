---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Semi_Normalization_Techniques
title: About semi-normalization techniques
# title: About semi-normalization techniques
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
date: 2024-08-31 09:00:00 +0900
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

## This is an article about semi-normalization techniques.

Hello!

Performance is a critical factor in database design.

Optimizing the performance of lookup operations is critical, especially in large databases or online Analytical Processing (OLAP) environments.

For this, a strategy called semi-normalization is used.

Today, we're going to talk about semi-normalization.

{:data-align="center"}

<!-- outline-end -->

## What is semi-regularization?

Semi-normalization is a technique that improves the performance of lookup operations by re-combining normalized tables.

It is mainly used in OLAP environments with many read operations, the process of increasing data redundancy and putting some normalized tables back together.

### the goal of semi-normalization

1. **Improves inquiry performance**: Improves the performance of frequently occurring inquiry operations.
2. **Reduce response times**: Reduce response times when running complex queries.
3. **Save storage**: Add redundant data to save storage space and optimize database capacity.

### Major semi-normalization techniques

1. **Pair tables**: Reunite normalized tables to optimize lookup operations.
2. **Add redundant data**: Adds redundant data to improve lookup performance.
3. **Add calculated fields**: Perform operations of data in advance, save it, and use it during query.

### Example

When dealing with customer order data, order information, customer information, and product information are stored separately in a normalized table.

By semi-normalizing this, you can improve the performance of lookup operations by storing customer and product information in duplicate in the order table.

## at the end of the day

Semi-normalization is one of the critical strategies for improving the performance of databases.

The user experience can be enhanced by re-combining normalized tables and adding redundant data to optimize lookup performance.

However, care must be taken to maintain data consistency and accuracy when applying semi-normalization.

That's it for the introduction of semi-regularization. See you again next time!
