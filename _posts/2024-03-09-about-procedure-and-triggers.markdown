---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Procedure_And_Triggers
title: About procedures and triggers
# title: About procedures and triggers
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: SQL
# multiple tag entries are possible
tags: [sql]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-03-09 09:00:00 +0900
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

## This is an article about procedures and triggers.

hello everyone! Today, we will learn about ‘procedures’ and ‘triggers’, which play important roles in database management.

Both features greatly help automate database operations and increase efficiency.

{:data-align="center"}

<!-- outline-end -->

### Procedure

A procedure is a function that allows a series of SQL commands to be executed as a single function in the database.

This means you can process complex queries that are used multiple times in one go.

This reduces code duplication and makes maintenance convenient.

A procedure is not executed until it is called, either by an explicit request from the user or by another trigger or procedure.

Additionally, you can receive parameters within a procedure and perform operations dynamically.

### Trigger

A trigger is a procedure that is automatically executed in the database when a specific event (data insertion, modification, deletion, etc.) occurs.

This allows you to ensure data consistency, automatically check that certain conditions are met, or process complex business rules within the database.

Triggers are automatically executed when certain conditions are met without any explicit call from the user.

This maintains the integrity of the database and enables efficient data management.

## summary

If you understand the characteristics of procedures and triggers and utilize them well, you can perform database operations more efficiently.

This reduces the complexity of database management and increases the accuracy and stability of operations.
