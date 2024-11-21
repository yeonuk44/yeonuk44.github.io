---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Get_The_Number_You_Caught
title: Get the number you caught (with.MySQL)
# title: Get the number you caught (with.MySQL)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Sql
# multiple tag entries are possible
tags: [sql, coding test]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-11-21 09:00:00 +0900
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

## This is an article about saving the number caught (with.MySQL).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Please write a SQL statement that outputs the number of fish that are 10cm or less in length among the caught fish.

Please name the column representing the number of fish as FISH_COUNT.

Problem Description

The FISH_INFO table used by the fishing app contains information on fish caught.

The structure of the FISH_INFO table is as follows, and ID, FISH_TYPE, LENGTH, and TIME indicate the ID of the fish caught, the type of fish (number), the length of the fish caught (cm), and the date of the fish caught.

#### USER_INFO Table

<!-- #### restrictions

- The length of a is not less than 1 but not more than 1,000,000.
- a[i] means the number written on the i+1th balloon.
- All numbers of a are integers greater than or equal to -1,000,000 and less than or equal to 1,000,000,000.
- All numbers of a are different -->

<!-- #### I/O Yes -->

| Column name | Type    | Nullable |
| ----------- | ------- | -------- |
| ID          | INTEGER | FALSE    |
| FISH_TYPE   | INTEGER | FALSE    |
| LENGTH      | FLOAT   | TRUE     |
| TIME        | DATE    | FALSE    |

However, if the caught fish is less than 10 cm long, the LENGTH is NULL, and there is no NULL in the LENGTH.

### problem solving

```sql
SELECT COUNT(*) AS FISH_COUNT
FROM FISH_INFO
WHERE LENGTH <= 10 OR LENGTH IS NULL;
```

#### Solution Description

This SQL query calculates and returns the number of fish that meet a specific condition.

The query extracts data from the FISH_INFO table, and the main components are.

First, the SELECT section specifies the value to look up.

COUNT(\*) AS FISH_COUNT calculates the number of records (i.e., fish) that meet the condition and outputs the result under the alias FISH_COUNT.

This means the total number of fish that meet the conditions.

The FROM section then specifies the default table on which to run the query.

In this case, the FISH_INFO table is used.

Next, in the WHERE section, you set specific conditions to filter the data you need.

The condition, LENGTH IS NULL, selects a fish with no length information, i.e., a value of NULL.

This query calculates the total number of fish with a length of 10 or less and returns them to FISH_COUNT.
