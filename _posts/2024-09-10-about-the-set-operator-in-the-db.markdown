---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_The_Set_Operator_In_The_DB
title: About the set operator in the DB
# title: About the set operator in the DB
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
date: 2024-09-10 09:00:00 +0900
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

## This article examines the set operator of the DB.

Hello!

In databases, set operators are used to combine or divide data extracted from multiple tables.

These set operators manipulate and combine two or more sets to produce new results.

Now let's look at the main types of database set operators.

{:data-align="center"}

<!-- outline-end -->

## United operator (UNION)

The UNION operator combines two sets of results to return the result of removing duplicate rows.

In other words, it creates a result set that contains all rows belonging to both sets.

This allows you to combine two sets from the database into a single set of results.

### Intersection operator (INTERSECT)

The INTERSECT operator selects and returns only common rows from the two result sets.

In other words, it creates a result set that contains only rows that belong to both sets at the same time.

This allows you to find the intersection of two sets in the database.

### Difference set operator (EXCEPT or MINUS)

The EXCEPT or MINUS operator returns a result that excludes the row of the second result set from the first result set.

That is, it creates a result set that contains only rows that belong to the first set and not to the second.

This allows you to find a difference set of two sets in the database.

### Cross-combination operator (CROSS JOIN or CARTESIAN JOIN)

The CROSS JOIN operator returns a set created by combining all rows of two tables.

That is, for each row in the first table, all rows in the second table are combined to generate a set of results.

This allows you to find all possible combinations of two tables in the database.

### Association Operator (JOIN)

The JOIN operator is used to combine two or more tables into a single set of results.

Combine tables based on specific conditions and combine data based on specific columns.

There are various kinds of combining operators, such as INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL OUTER JOIN, etc.

## at the end of the day

The database set operator is utilized as an important tool for combining and segmenting data.

These operators can be appropriately utilized to easily obtain the desired results from the database.

It is important to understand and utilize the set operator well when dealing with databases.

Thank you!
