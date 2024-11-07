---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Get_The_Products_And_Membership_Lists_That_Have_Been_Repurchased
title: Get the products and membership lists that have been repurchased (with.MySQL)
# title: Get the products and membership lists that have been repurchased (with.MySQL)
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
date: 2024-11-07 09:00:00 +0900
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

## This is an article about the products that have been repurchased and the membership list (with.MySQL).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

From the ONLINE_SALE table, obtain the data of the same member repurchasing the same product, and write a SQL statement that outputs the repurchased member ID and repurchased product ID.

Please arrange the results in ascending order based on the member ID and if the member ID is the same, please arrange them in descending order based on the product ID.

Problem Description

The following is the ONLINE_SALE table containing online product sales information of a clothing shopping mall.

The ONLINE_SALE table is structured as follows, and ONLINE_SALE_ID, USER_ID, PRODUCT_ID, SALES_AMOUNT, SALES_DATE represents online product sales ID, member ID, product sales volume, and sales date, respectively.

#### ONLINE_SALE table

<!-- #### restrictions

- The length of a is not less than 1 but not more than 1,000,000.
- a[i] means the number written on the i+1th balloon.
- All numbers of a are integers greater than or equal to -1,000,000 and less than or equal to 1,000,000,000.
- All numbers of a are different -->

<!-- #### I/O Yes -->

| Column name    | Type    | Nullable |
| -------------- | ------- | -------- |
| ONLINE_SALE_ID | INTEGER | FALSE    |
| USER_ID        | INTEGER | FALSE    |
| PRODUCT_ID     | INTEGER | FALSE    |
| SALES_AMOUNT   | INTEGER | FALSE    |
| SALES_DATE     | DATE    | FALSE    |

Only one sales data exists for the same date, member ID, and product ID combination.

### problem solving

```sql
SELECT USER_ID, PRODUCT_ID
FROM ONLINE_SALE
GROUP BY USER_ID, PRODUCT_ID
HAVING COUNT(*) >= 2
ORDER BY USER_ID, PRODUCT_ID DESC;
```

#### Solution Description

This SQL query queries information about goods purchased more than once by a particular user and returns results sorted by user ID and product ID.

The query extracts data from the ONLINE_SALE table, and the main components are as follows.

First, the SELECT section specifies the columns to look up.

USER_ID is the user's unique identifier, PRODUCT_ID is the product's unique identifier, which outputs these two columns as a result.

The FROM section then specifies the default table on which to run the query.

In this case, the ONLINE_SALE table is used.

Next, the GROUP BY section groups the data based on USER_ID and PRODUCT_ID.

This allows you to group purchase records by each user and product combination.

The HAVING section then selects only groups that meet specific conditions among grouped data.

HAVING COUNT(\*) >=2 selects when there are more than two records in the group.

This means that a particular user has purchased the same product more than once.

Finally, sort the results through the ORDER BY clause.

Sort in ascending order based on USER_ID, and within the same user, sort in descending order based on PRODUCT_ID.

This allows each user to view items purchased more than once in order of user ID.

This query allows you to query the user ID and product ID of a product that a particular user has purchased more than once.

This allows you to analyze recurring purchase patterns and get insights on specific users and product combinations.
