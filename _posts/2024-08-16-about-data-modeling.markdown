---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Data_Modeling
title: About Data Modeling
# title: About Data Modeling
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Data
# multiple tag entries are possible
tags: [data]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-08-16 09:00:00 +0900
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

## This is an article about data modeling.

Hello!

Today, we will learn about data modeling.

As data has become a key asset in modern business, it has become critical to understand and manage it effectively.

One of the key tools for managing such data is data modeling.

We'll learn what data modeling is, why it's important, and how it's done.

{:data-align="center"}

<!-- outline-end -->

## What is data modeling

Data modeling is the process of organizing and organizing data systematically.

It is used to design database systems by visually representing the characteristics and relationships of the data.

Data modeling is typically divided into three main steps.

### Conceptual Data Modeling

Define the overall structure of data reflecting business requirements at a high level.

Mainly uses an entity (ERD) and an entity-relationhip diagram (ERD) that represents the relationship between them.

### Logical Data Modeling

We detail the logical structure of the data based on conceptual models.

This step defines tables, columns, data types, etc., and minimizes data duplication through the normalization process.

### Physical Data Modeling

We design a physical structure for implementing logical models in a real database.

This includes index design, partitioning, and storage settings that take into account the performance of the database.

## The Importance of Data Modeling

### Ensuring Data Integrity

Data modeling plays an important role in maintaining data consistency and integrity.

A systematic data structure minimizes data redundancy and ensures the accuracy of the data.

### Efficient Data Management

Organizing data systematically through data modeling improves database performance and facilitates management.

This allows tasks such as lookup, insertion, update, and deletion of data to be performed more efficiently.

### Reflect business requirements

By clearly identifying and reflecting business requirements in the data modeling process and data structures, databases can be designed for real business environments.

This goes a long way to support data-driven decision-making.

## at the end of the day

We've learned about modeling the ideal data.

Have a great day!
