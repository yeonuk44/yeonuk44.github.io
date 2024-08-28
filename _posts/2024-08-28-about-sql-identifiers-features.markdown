---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_SQL_Identifiers_Features
title: About SQL Identifier Features
# title: About SQL Identifier Features
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
date: 2024-08-28 09:00:00 +0900
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

## This article examines the identifier characteristics of SQL.

Hello!

Today, we will learn about the characteristics of the identifiers used in the database.

Identifiers are important elements used to uniquely identify each row in the database and must have the following characteristics.

{:data-align="center"}

<!-- outline-end -->

## Unique (Unique)

### Overview

Unique means that each identifier value is unique.

This means that the same value must not appear more than once.

### Example

Each student's student number or each product's unique product code must be unique.

## Minimum

### Overview

Minimal means that the identifier should be as small and concise as possible.

In other words, you should use identifiers to identify your data only as much as you need.

### Example

It is recommended that you select your student number as an identifier using only the minimum amount of information required to uniquely identify the student.

There is no need to use the student's name or address additionally other than the student number.

## Immutability

### Overview

The invariance means that the identifier value should not change.

This means that the identifier value once specified should remain unchanged.

### Example

The student's student number or product code of the product should not change once it has been created.

## at the end of the day

Identifiers are important elements used to uniquely identify each row in the database.

These identifiers must have characteristics such as uniqueness, minimum, and invariance to ensure the accuracy and consistency of the database.

It is important to select and manage identifiers in consideration of these features when designing a database.

I hope this post helped me understand the features of the identifier.

In the next post, we will take a closer look at the types of identifiers and how to use them.

Let's study together!
