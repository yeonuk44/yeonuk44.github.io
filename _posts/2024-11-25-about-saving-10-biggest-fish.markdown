---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Saving_10_Biggest_Fish
title: Saving 10 Biggest Fish (with.MySQL)
# title: Saving 10 Biggest Fish (with.MySQL)
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
date: 2024-11-25 09:00:00 +0900
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

## Here's a look at saving 10 of the biggest fish (with.MySQL).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Please write a SQL statement that outputs the ID and length of the 10 largest fish in the FISH_INFO table.

Please sort the results in descending order based on the length, and if the lengths are the same, please sort in ascending order for the fish's ID.

However, none of the 10 largest fish are less than 10 cm long.

ID column name should be ID and length column name should be LENGTH.

Problem Description

The FISH_INFO table used by the fishing app contains information on fish caught.

The structure of the FISH_INFO table is as follows, and ID, FISH_TYPE, LENGTH, and TIME indicate the ID of the fish caught, the type of fish (number), the length of the fish caught (cm), and the date of the fish caught.

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

### problem solving

```sql
SELECT ID, LENGTH
FROM FISH_INFO
ORDER BY LENGTH DESC, ID
LIMIT 10;
```

#### Solution Description

This SQL query queries and returns the top 10 data based on fish length information.

The query extracts data from the FISH_INFO table, and the main components are.

First, the SELECT section specifies the columns to look up.

ID is the unique identifier of the fish, LENGTH is the length of the fish, and these two columns are output as a result.

The FROM section then specifies the default table on which to run the query.

In this case, the FISH_INFO table is used.

Next, sort the results through the ORDER BY clause.

There are two sorting criteria, the first is LENGTH DESC.

These are arranged in descending order based on the length of the fish, starting with the largest fish.

The second sorting criterion is ID, and if the lengths are the same, sort them in ascending order based on ID.

This allows fish of the same length to be aligned in order of unique ID.

Finally, LIMIT 10 selects and returns only the top 10 rows from the query results.

It serves to return information about the 10 largest fish among the sorted results.

This query allows you to look up the IDs and lengths of the 10 largest fish.

This makes it easy to analyze fish of a specific size or larger or to identify the top fish by size.
