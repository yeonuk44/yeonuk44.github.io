---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Storage_Modules_And_PL_SQL
title: About storage modules and PL/SQL
# title: About storage modules and PL/SQL
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
date: 2024-09-13 09:00:00 +0900
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

## This article is about the storage module and PL/SQL.

Hello!

Storage modules and PL/SQL are powerful tools used to create and manage procedures in databases.

They allow you to efficiently perform tasks and manage your data in the database.

Now let's talk about the storage module and PL/SQL.

{:data-align="center"}

<!-- outline-end -->

## Stored Module

A storage module is a program-level code that is predefined and stored to perform specific tasks in a database.

It is mainly used in the form of storage procedures, storage functions, and storage triggers.

These storage modules can efficiently manage and execute tasks that are repeatedly performed in the database.

### PL/SQL(Procedural Language/Structured Query Language)

PL/SQL is a procedural programming language developed by Oracle that is used to create and manage procedures in databases.

By combining the characteristics of SQL statements and programming languages, complex tasks can be performed in databases.

PL/SQL is used in the form of storage procedures, storage functions, and storage triggers.

### Utilize storage modules and PL/SQL

- **Stored Procedure**: Store procedural code for performing specific tasks and call it when needed. It is used to simplify and increase reuse of tasks in databases.

- **Stored Function**: Save a function that returns a specific value and calls it when needed. It can be used by calling as a function in SQL statements and can easily implement complex calculations or logic.

- **Stored Trigger**: Save and use code that runs automatically when a particular event occurs. Used to maintain data consistency or monitor certain conditions.

### Benefits of storage modules and PL/SQL

- **Effective data handling**: Use storage modules and PL/SQL to efficiently handle complex tasks in databases.
- **Reusable**: Create a written procedure or function can be called and reused whenever necessary, which can reduce development time and facilitate maintenance.
- **Enhance database performance**: Use storage modules and PL/SQL to improve database performance.

## at the end of the day

Storage modules and PL/SQL serve as critical tools for creating and managing procedures in databases.

They allow you to efficiently perform tasks and manage data in databases, reduce development time and increase maintenance.

When dealing with databases, it is important to leverage storage modules and PL/SQL appropriately to increase the efficiency of data management.

Thank you!
