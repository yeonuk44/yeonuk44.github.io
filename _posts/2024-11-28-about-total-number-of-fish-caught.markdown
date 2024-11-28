---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Total_Number_Of_Fish_Caught
title: Total number of fish caught (with.MySQL)
# title: Total number of fish caught (with.MySQL)
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
date: 2024-11-28 09:00:00 +0900
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

## This is an article about the total number of fish caught (with.MySQL).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Please write a SQL statement that outputs the number of BASS and SNAPPER caught in the FISH_INFO table.

Please name the column 'FISH_COUNT'.

Problem Description

The FISH_INFO table used by the fishing app contains information on fish caught.

The structure of the FISH_INFO table is as follows, and ID, FISH_TYPE, LENGTH, and TIME indicate the ID of the fish caught, the type of fish (number), the length of the fish caught (cm), and the date of the fish caught.

The FISH_NAME_INFO table contains information about the name of the fish.

The structure of the FISH_NAME_INFO table is as follows, where FISH_TYPE and FISH_NAME are fish types (numbers) and fish names (characters), respectively.

#### FISH_INFO Table

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

| Column name | Type    | Nullable |
| ----------- | ------- | -------- |
| FISH_TYPE   | INTEGER | FALSE    |
| FISH_NAME   | VARCHAR | FALSE    |

### problem solving

```sql
SELECT COUNT(FN.FISH_TYPE) AS FISH_COUNT
FROM FISH_INFO AS FI JOIN FISH_NAME_INFO AS FN ON FI.FISH_TYPE = FN.FISH_TYPE
WHERE FISH_NAME LIKE 'BASS' OR FISH_NAME LIKE 'SNAPPER';
```

#### Solution Description

This SQL query calculates and returns the number of fish of a particular kind (BASS or SNAPPER).

The query extracts the data by joining the FISH_INFO table and the FISH_NAME_INFO table, with key components as follows.

First, the SELECT section specifies the value to look up.

COUNT (FN.FISH_TYPE) AS FISH_COUNT counts the types of fish that meet the conditions and outputs the number as FISH_COUNT alias.

This refers to the total number of fish corresponding to BASS or SNAPPER.

The FROM section then specifies the default table on which to run the query.

Here, we use the FISH_INFO table, which we alias FI.

Next, use the JOIN clause to join the FISH_NAME_INFO table with the FISH_INFO table.

The condition of the join is FI.FISH_TYPE = FN.FISH_TYPE, which is linked based on the FISH_TYPE columns of both tables.

By doing so, you can combine fish information and fish name information to inquire.

In the WHERE section, you set specific conditions to filter the required data.

The FISH_NAME LIKE 'BASS' OR FISH_NAME LIKE 'SNAPPER' condition selects when the fish is named 'BASS' or 'SNAPPER'.

Under these conditions, only fish named BASS and SNAPPER will be selected.

This query allows you to calculate the total number of fish named BASS or SNAPPER and return them to FISH_COUNT.

This makes it easy to identify a specific type of fish population and can be useful for analysis or statistics on a specific fish species.
